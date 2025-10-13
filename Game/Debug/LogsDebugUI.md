# Game.Debug.LogsDebugUI

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `DebugContainer`  

## Code

```csharp
public static class LogsDebugUI
{
    internal static UnityEngine.GUIContent <BuildLogsDebugUI>g__ToTitleCase|1_0(System.String input);
    private static System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildLogsDebugUI();
    private static System.Void Rebuild();
}
```


## Methods

- `internal static <BuildLogsDebugUI>g__ToTitleCase|1_0(System.String input) : UnityEngine.GUIContent`  

```csharp
internal static UnityEngine.GUIContent <BuildLogsDebugUI>g__ToTitleCase|1_0(System.String input);
```

- `private static BuildLogsDebugUI() : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private static List<DebugUI.Widget> BuildLogsDebugUI()
	{
		DebugUI.Container container = new DebugUI.Container();
		List<Level> levels = Level.GetLevels().ToList();
		foreach (ILog log in LogManager.GetAllLoggers())
		{
			container.children.Add(new DebugUI.EnumField
			{
				displayName = log.name,
				getter = () => log.effectivenessLevel.severity,
				setter = delegate(int value)
				{
					log.effectivenessLevel = Level.GetLevel(value);
				},
				getIndex = () => levels.FindIndex((Level level) => level == log.effectivenessLevel),
				setIndex = delegate(int index)
				{
					log.effectivenessLevel = levels[index = (index + levels.Count) % levels.Count];
				},
				enumNames = levels.Select((Level level) => ToTitleCase(level.name)).ToArray(),
				enumValues = levels.Select((Level level) => level.severity).ToArray()
			});
			DebugUI.Container container2 = new DebugUI.Container();
			container2.children.Add(new DebugUI.BoolField
			{
				displayName = "Show errors in UI",
				getter = () => log.showsErrorsInUI,
				setter = delegate(bool v)
				{
					log.showsErrorsInUI = v;
				}
			});
			container2.children.Add(new DebugUI.BoolField
			{
				displayName = "Log stack trace",
				getter = () => log.logStackTrace,
				setter = delegate(bool v)
				{
					log.logStackTrace = v;
				}
			});
			if (GameManager.instance.configuration.qaDeveloperMode)
			{
				container2.children.Add(new DebugUI.BoolField
				{
					displayName = "Disable backtrace",
					getter = () => log.disableBacktrace,
					setter = delegate(bool v)
					{
						log.disableBacktrace = v;
					}
				});
			}
			container2.children.Add(new DebugUI.EnumField
			{
				displayName = "Show stack trace below levels",
				getter = () => log.showsStackTraceAboveLevels.severity,
				setter = delegate(int value)
				{
					log.showsStackTraceAboveLevels = Level.GetLevel(value);
				},
				getIndex = () => levels.FindIndex((Level level) => level == log.showsStackTraceAboveLevels),
				setIndex = delegate(int index)
				{
					log.showsStackTraceAboveLevels = levels[index = (index + levels.Count) % levels.Count];
				},
				enumNames = levels.Select((Level level) => ToTitleCase(level.name)).ToArray(),
				enumValues = levels.Select((Level level) => level.severity).ToArray()
			});
			container.children.Add(container2);
		}
		return new List<DebugUI.Widget>
		{
			new DebugUI.Button
			{
				displayName = "Refresh",
				action = Rebuild
			},
			container
		};
		static GUIContent ToTitleCase(string input)
		{
			return new GUIContent(char.ToUpper(input[0]) + input.Substring(1).ToLower());
		}
	}
```

- `private static Rebuild() : System.Void`  

```csharp
private static void Rebuild()
	{
		DebugSystem.Rebuild(BuildLogsDebugUI);
	}
```


## Nested types

- `Game.Debug.LogsDebugUI+<>c`  
- `Game.Debug.LogsDebugUI+<>c__DisplayClass1_0`  
- `Game.Debug.LogsDebugUI+<>c__DisplayClass1_1`  

