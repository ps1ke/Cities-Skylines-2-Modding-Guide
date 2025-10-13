# Game.Debug.TestsDebugUI

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `DebugContainer`  

## Code

```csharp
public static class TestsDebugUI
{
    private static System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildTestScenariosDebugUI();
}
```


## Methods

- `private static BuildTestScenariosDebugUI() : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private static List<DebugUI.Widget> BuildTestScenariosDebugUI()
	{
		if (!GameManager.instance.configuration.qaDeveloperMode)
		{
			return null;
		}
		List<DebugUI.Widget> list = new List<DebugUI.Widget>();
		TestScenarioSystem tss = TestScenarioSystem.instance;
		Dictionary<Category, DebugUI.Foldout> dictionary = new Dictionary<Category, DebugUI.Foldout>();
		foreach (KeyValuePair<string, TestScenarioSystem.Scenario> scenario in tss.scenarios)
		{
			if (!dictionary.TryGetValue(scenario.Value.category, out var value))
			{
				value = new DebugUI.Foldout
				{
					displayName = scenario.Value.category.ToString()
				};
				dictionary.Add(scenario.Value.category, value);
				list.Add(value);
			}
			value.children.Add(new DebugUI.Button
			{
				displayName = scenario.Key,
				action = delegate
				{
					tss.RunScenario(scenario.Key, CancellationToken.None);
				}
			});
		}
		return list;
	}
```


## Nested types

- `Game.Debug.TestsDebugUI+<>c__DisplayClass0_0`  
- `Game.Debug.TestsDebugUI+<>c__DisplayClass0_1`  

