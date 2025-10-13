# Game.UI.Widgets.PagedBindings

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Widgets.IWidgetBindingFactory`  

## Code

```csharp
public class PagedBindings : Game.UI.Widgets.IWidgetBindingFactory
{
    public PagedBindings();

    public System.Collections.Generic.IEnumerable<Colossal.UI.Binding.IBinding> CreateBindings(System.String group, Colossal.UI.Binding.IReader<Game.UI.Widgets.IWidget> pathResolver, Game.UI.Widgets.ValueChangedCallback onValueChanged);
}
```


## Constructors

- `public PagedBindings()`  

```csharp
public PagedBindings();
```


## Methods

- `public CreateBindings(System.String group, Colossal.UI.Binding.IReader<Game.UI.Widgets.IWidget> pathResolver, Game.UI.Widgets.ValueChangedCallback onValueChanged) : System.Collections.Generic.IEnumerable<Colossal.UI.Binding.IBinding>`  

```csharp
public IEnumerable<IBinding> CreateBindings(string group, IReader<IWidget> pathResolver, ValueChangedCallback onValueChanged)
	{
		yield return new TriggerBinding<IWidget, int>(group, "setCurrentPageIndex", delegate(IWidget widget, int pageIndex)
		{
			if (widget is IPaged paged)
			{
				paged.currentPageIndex = pageIndex;
			}
			else
			{
				UnityEngine.Debug.LogError((widget != null) ? "Widget does not implement IPaged" : "Invalid widget path");
			}
		}, pathResolver);
	}
```


## Nested types

- `Game.UI.Widgets.PagedBindings+<>c`  
- `Game.UI.Widgets.PagedBindings+<CreateBindings>d__0`  

