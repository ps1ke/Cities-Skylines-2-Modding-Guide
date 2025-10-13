# Game.Debug.LocalizationDebugUI

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

**Attributes:** `DebugContainer`  

## Code

```csharp
public class LocalizationDebugUI : System.IDisposable
{
    private System.Int32 m_SelectedContentId;
    private static readonly UnityEngine.GUIContent[] kLocalizationDebugModeStrings;

    public LocalizationDebugUI();

    private System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildLocalizationDebugUI(Unity.Entities.World world);
    public System.Void Dispose();
    private System.Void InitLocalization(System.Int32 contentId);
    private System.Void Rebuild();
}
```


## Fields

- `private System.Int32 m_SelectedContentId`  

```csharp
private System.Int32 m_SelectedContentId;
```

- `private static readonly UnityEngine.GUIContent[] kLocalizationDebugModeStrings`  

```csharp
private static readonly UnityEngine.GUIContent[] kLocalizationDebugModeStrings;
```


## Constructors

- `public LocalizationDebugUI()`  

```csharp
public LocalizationDebugUI()
	{
		InitLocalization(m_SelectedContentId);
	}
```


## Methods

- `private BuildLocalizationDebugUI(Unity.Entities.World world) : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private List<DebugUI.Widget> BuildLocalizationDebugUI(World world)
	{
		LocalizationManager manager = GameManager.instance.localizationManager;
		if (manager == null)
		{
			return null;
		}
		string[] locales = manager.GetSupportedLocales();
		GUIContent[] array = new GUIContent[locales.Length];
		int[] array2 = new int[locales.Length];
		for (int i = 0; i < locales.Length; i++)
		{
			array[i] = new GUIContent(locales[i]);
			array2[i] = i;
		}
		return new List<DebugUI.Widget>
		{
			new DebugUI.EnumField
			{
				displayName = "Language",
				getter = () => Array.IndexOf(locales, manager.activeDictionary.localeID),
				setter = delegate(int value)
				{
					manager.SetActiveLocale(locales[value]);
				},
				enumNames = array,
				enumValues = array2,
				getIndex = () => Array.IndexOf(locales, manager.activeDictionary.localeID),
				setIndex = delegate
				{
				}
			},
			new DebugUI.EnumField
			{
				displayName = "Debug Mode",
				getter = () => (int)GameManager.instance.userInterface.localizationBindings.debugMode,
				setter = delegate(int value)
				{
					GameManager.instance.userInterface.localizationBindings.debugMode = (LocalizationBindings.DebugMode)value;
				},
				enumNames = kLocalizationDebugModeStrings,
				autoEnum = typeof(LocalizationBindings.DebugMode),
				getIndex = () => (int)GameManager.instance.userInterface.localizationBindings.debugMode,
				setIndex = delegate
				{
				}
			},
			new DebugUI.Button
			{
				displayName = "Print input bindings and controls",
				action = delegate
				{
					List<string> list = new List<string>();
					List<string> list2 = new List<string>();
					foreach (ProxyBinding binding in InputManager.instance.GetBindings(InputManager.PathType.Effective, InputManager.BindingOptions.OnlyRebindable))
					{
						if (!list.Contains(binding.title))
						{
							list.Add(binding.title);
						}
						foreach (string item2 in binding.ToHumanReadablePath())
						{
							string item = binding.device.ToString() + "." + item2;
							if (!list2.Contains(item))
							{
								list2.Add(item);
							}
						}
					}
					UnityEngine.Debug.Log(string.Join("\n", list.Select(delegate(string b)
					{
						string text = b.Substring(b.IndexOf("/", StringComparison.InvariantCulture) + 1).Replace("/binding", "");
						return "Options.OPTION[" + b + "]\t" + text + "\nOptions.OPTION_DESCRIPTION[" + b + "]\tTBD";
					})));
					list2.Sort();
					UnityEngine.Debug.Log(string.Join("\n", list2.Select((string p) => "Options.INPUT_CONTROL[" + p + "]\t" + p.Substring(p.IndexOf(".", StringComparison.InvariantCulture) + 1))));
				}
			},
			new DebugUI.Button
			{
				displayName = "Print asset categories",
				action = delegate
				{
					EditorAssetCategorySystem orCreateSystemManaged = world.GetOrCreateSystemManaged<EditorAssetCategorySystem>();
					StringBuilder stringBuilder = new StringBuilder();
					foreach (EditorAssetCategory category in orCreateSystemManaged.GetCategories())
					{
						stringBuilder.AppendLine(category.GetLocalizationID() + "," + category.id);
					}
					string path = Path.Combine(EnvPath.kUserDataPath, "category_locale.csv");
					using FileStream stream = (File.Exists(path) ? File.OpenWrite(path) : File.Create(path));
					using StreamWriter streamWriter = new StreamWriter(stream);
					streamWriter.Write(stringBuilder);
				}
			}
		};
	}
```

- `public Dispose() : System.Void`  

```csharp
public void Dispose()
	{
	}
```

- `private InitLocalization(System.Int32 contentId) : System.Void`  

```csharp
private void InitLocalization(int contentId)
	{
	}
```

- `private Rebuild() : System.Void`  

```csharp
private void Rebuild()
	{
		DebugSystem.Rebuild(BuildLocalizationDebugUI);
	}
```


## Nested types

- `Game.Debug.LocalizationDebugUI+<>c`  
- `Game.Debug.LocalizationDebugUI+<>c__DisplayClass6_0`  

