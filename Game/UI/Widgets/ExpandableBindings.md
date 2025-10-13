# Game.UI.Widgets.ExpandableBindings

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Widgets.IWidgetBindingFactory`  

## Code

```csharp
public class ExpandableBindings : Game.UI.Widgets.IWidgetBindingFactory
{
    public ExpandableBindings();

    public System.Collections.Generic.IEnumerable<Colossal.UI.Binding.IBinding> CreateBindings(System.String group, Colossal.UI.Binding.IReader<Game.UI.Widgets.IWidget> pathResolver, Game.UI.Widgets.ValueChangedCallback onValueChanged);
}
```


## Constructors

- `public ExpandableBindings()`  

```csharp
public ExpandableBindings();
```


## Methods

- `public CreateBindings(System.String group, Colossal.UI.Binding.IReader<Game.UI.Widgets.IWidget> pathResolver, Game.UI.Widgets.ValueChangedCallback onValueChanged) : System.Collections.Generic.IEnumerable<Colossal.UI.Binding.IBinding>`  

```csharp
public IEnumerable<IBinding> CreateBindings(string group, IReader<IWidget> pathResolver, ValueChangedCallback onValueChanged)
	{
		yield return new TriggerBinding<IWidget, bool>(group, "setExpanded", delegate(IWidget widget, bool expanded)
		{
			if (widget is IExpandable expandable)
			{
				expandable.expanded = expanded;
			}
			else
			{
				UnityEngine.Debug.LogError((widget != null) ? "Widget does not implement IExpandable" : "Invalid widget path");
			}
		}, pathResolver);
	}
```


## Nested types

- `Game.UI.Widgets.ExpandableBindings+<>c`  
- `Game.UI.Widgets.ExpandableBindings+<CreateBindings>d__0`  

