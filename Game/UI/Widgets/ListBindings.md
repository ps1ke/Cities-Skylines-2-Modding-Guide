# Game.UI.Widgets.ListBindings

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Widgets.IWidgetBindingFactory`  

## Code

```csharp
public class ListBindings : Game.UI.Widgets.IWidgetBindingFactory
{
    public ListBindings();

    public System.Collections.Generic.IEnumerable<Colossal.UI.Binding.IBinding> CreateBindings(System.String group, Colossal.UI.Binding.IReader<Game.UI.Widgets.IWidget> pathResolver, Game.UI.Widgets.ValueChangedCallback onValueChanged);
}
```


## Constructors

- `public ListBindings()`  

```csharp
public ListBindings();
```


## Methods

- `public CreateBindings(System.String group, Colossal.UI.Binding.IReader<Game.UI.Widgets.IWidget> pathResolver, Game.UI.Widgets.ValueChangedCallback onValueChanged) : System.Collections.Generic.IEnumerable<Colossal.UI.Binding.IBinding>`  

```csharp
public IEnumerable<IBinding> CreateBindings(string group, IReader<IWidget> pathResolver, ValueChangedCallback onValueChanged)
	{
		yield return new TriggerBinding<IWidget>(group, "addListElement", delegate(IWidget widget)
		{
			if (widget is IListWidget listWidget)
			{
				listWidget.AddElement();
				onValueChanged(widget);
			}
			else
			{
				UnityEngine.Debug.LogError((widget != null) ? "Widget does not implement IListContainer" : "Invalid widget path");
			}
		}, pathResolver);
		yield return new TriggerBinding<IWidget, int>(group, "duplicateListElement", delegate(IWidget widget, int index)
		{
			if (widget is IListWidget listWidget)
			{
				listWidget.DuplicateElement(index);
				onValueChanged(widget);
			}
			else
			{
				UnityEngine.Debug.LogError((widget != null) ? "Widget does not implement IListContainer" : "Invalid widget path");
			}
		}, pathResolver);
		yield return new TriggerBinding<IWidget, int, int>(group, "moveListElement", delegate(IWidget widget, int fromIndex, int toIndex)
		{
			if (widget is IListWidget listWidget)
			{
				listWidget.MoveElement(fromIndex, toIndex);
				onValueChanged(widget);
			}
			else
			{
				UnityEngine.Debug.LogError((widget != null) ? "Widget does not implement IListContainer" : "Invalid widget path");
			}
		}, pathResolver);
		yield return new TriggerBinding<IWidget, int>(group, "deleteListElement", delegate(IWidget widget, int index)
		{
			if (widget is IListWidget listWidget)
			{
				listWidget.DeleteElement(index);
				onValueChanged(widget);
			}
			else
			{
				UnityEngine.Debug.LogError((widget != null) ? "Widget does not implement IListContainer" : "Invalid widget path");
			}
		}, pathResolver);
		yield return new TriggerBinding<IWidget>(group, "clearList", delegate(IWidget widget)
		{
			if (widget is IListWidget listWidget)
			{
				listWidget.Clear();
				onValueChanged(widget);
			}
			else
			{
				UnityEngine.Debug.LogError((widget != null) ? "Widget does not implement IListContainer" : "Invalid widget path");
			}
		}, pathResolver);
	}
```


## Nested types

- `Game.UI.Widgets.ListBindings+<>c__DisplayClass0_0`  
- `Game.UI.Widgets.ListBindings+<CreateBindings>d__0`  

