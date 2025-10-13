# Game.Debug.UIBindingDebugUI

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `DebugContainer`  

## Code

```csharp
public static class UIBindingDebugUI
{
    private static System.Void AddBindingButtonsRecursive(Game.UI.Debug.DebugUISystem debugUIsystem, System.Collections.Generic.Dictionary<System.String, UnityEngine.Rendering.DebugUI+Container> containers, Colossal.UI.Binding.IBindingGroup group);
    private static System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildUIBindingsDebugUI(Unity.Entities.World world);
    private static System.String FormatGenericTypeString(System.Type t);
    private static System.Void Rebuild();
}
```


## Methods

- `private static AddBindingButtonsRecursive(Game.UI.Debug.DebugUISystem debugUIsystem, System.Collections.Generic.Dictionary<System.String, UnityEngine.Rendering.DebugUI+Container> containers, Colossal.UI.Binding.IBindingGroup group) : System.Void`  

```csharp
private static void AddBindingButtonsRecursive(DebugUISystem debugUIsystem, Dictionary<string, DebugUI.Container> containers, IBindingGroup group)
	{
		foreach (IBinding binding in group.bindings)
		{
			IDebugBinding debugBinding = binding as IDebugBinding;
			if (debugBinding != null)
			{
				if (!containers.TryGetValue(debugBinding.group, out var value))
				{
					value = new DebugUI.Foldout(debugBinding.group, new ObservableList<DebugUI.Widget>());
					containers.Add(debugBinding.group, value);
				}
				if (debugBinding.debugType == DebugBindingType.Trigger)
				{
					value.children.Add(new DebugUI.Button
					{
						displayName = debugBinding.name,
						action = delegate
						{
							debugUIsystem.Trigger(debugBinding);
						}
					});
				}
				else if (debugBinding.debugType == DebugBindingType.Event || debugBinding.debugType == DebugBindingType.Value)
				{
					value.children.Add(new DebugUI.BoolField
					{
						displayName = debugBinding.name,
						getter = () => debugUIsystem.observedBinding == debugBinding,
						setter = delegate(bool v)
						{
							debugUIsystem.observedBinding = (v ? debugBinding : null);
						}
					});
				}
				else
				{
					value.children.Add(new DebugUI.Value
					{
						displayName = debugBinding.name,
						getter = () => FormatGenericTypeString(debugBinding.GetType())
					});
				}
			}
			if (binding is IBindingGroup bindingGroup)
			{
				AddBindingButtonsRecursive(debugUIsystem, containers, bindingGroup);
			}
		}
	}
```

- `private static BuildUIBindingsDebugUI(Unity.Entities.World world) : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private static List<DebugUI.Widget> BuildUIBindingsDebugUI(World world)
	{
		DebugUISystem debugUISystem = world.GetOrCreateSystemManaged<DebugUISystem>();
		IBindingRegistry bindings = GameManager.instance.userInterface.bindings;
		Dictionary<string, DebugUI.Container> dictionary = new Dictionary<string, DebugUI.Container>();
		if (bindings != null)
		{
			AddBindingButtonsRecursive(debugUISystem, dictionary, bindings);
		}
		List<DebugUI.Widget> list = new List<DebugUI.Widget>();
		list.Add(new DebugUI.Button
		{
			displayName = "Refresh",
			action = Rebuild
		});
		list.Add(new DebugUI.Button
		{
			displayName = "Clear",
			action = delegate
			{
				debugUISystem.observedBinding = null;
			}
		});
		list.AddRange(dictionary.Values.OrderBy((DebugUI.Container container) => container.displayName));
		return list;
	}
```

- `private static FormatGenericTypeString(System.Type t) : System.String`  

```csharp
private static string FormatGenericTypeString(Type t)
	{
		if (!t.IsGenericType)
		{
			return t.Name;
		}
		string name = t.GetGenericTypeDefinition().Name;
		name = name.Substring(0, name.IndexOf('`'));
		string text = string.Join(",", t.GetGenericArguments().Select(FormatGenericTypeString).ToArray());
		return name + "<" + text + ">";
	}
```

- `private static Rebuild() : System.Void`  

```csharp
private static void Rebuild()
	{
		DebugSystem.Rebuild(BuildUIBindingsDebugUI);
	}
```


## Nested types

- `Game.Debug.UIBindingDebugUI+<>c`  
- `Game.Debug.UIBindingDebugUI+<>c__DisplayClass1_0`  
- `Game.Debug.UIBindingDebugUI+<>c__DisplayClass1_1`  
- `Game.Debug.UIBindingDebugUI+<>c__DisplayClass3_0`  

