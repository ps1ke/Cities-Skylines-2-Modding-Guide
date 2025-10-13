# Game.UI.Widgets.SettableBindings

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Widgets.IWidgetBindingFactory`  

## Code

```csharp
public class SettableBindings : Game.UI.Widgets.IWidgetBindingFactory
{
    public SettableBindings();

    public System.Collections.Generic.IEnumerable<Colossal.UI.Binding.IBinding> CreateBindings(System.String group, Colossal.UI.Binding.IReader<Game.UI.Widgets.IWidget> pathResolver, Game.UI.Widgets.ValueChangedCallback onValueChanged);
}
```


## Constructors

- `public SettableBindings()`  

```csharp
public SettableBindings();
```


## Methods

- `public CreateBindings(System.String group, Colossal.UI.Binding.IReader<Game.UI.Widgets.IWidget> pathResolver, Game.UI.Widgets.ValueChangedCallback onValueChanged) : System.Collections.Generic.IEnumerable<Colossal.UI.Binding.IBinding>`  

```csharp
public IEnumerable<IBinding> CreateBindings(string group, IReader<IWidget> pathResolver, ValueChangedCallback onValueChanged)
	{
		yield return new RawTriggerBinding(group, "setValue", delegate(IJsonReader reader)
		{
			pathResolver.Read(reader, out var value);
			if (value is ISettable settable)
			{
				settable.SetValue(reader);
				if (settable.shouldTriggerValueChangedEvent)
				{
					onValueChanged(value);
				}
			}
			else
			{
				reader.SkipValue();
				UnityEngine.Debug.LogError((value != null) ? "Widget does not implement ISettable" : "Invalid widget path");
			}
		});
	}
```


## Nested types

- `Game.UI.Widgets.SettableBindings+<>c__DisplayClass0_0`  
- `Game.UI.Widgets.SettableBindings+<CreateBindings>d__0`  

