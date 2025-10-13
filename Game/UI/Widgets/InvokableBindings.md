# Game.UI.Widgets.InvokableBindings

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Widgets.IWidgetBindingFactory`  

## Code

```csharp
public class InvokableBindings : Game.UI.Widgets.IWidgetBindingFactory
{
    public InvokableBindings();

    public System.Collections.Generic.IEnumerable<Colossal.UI.Binding.IBinding> CreateBindings(System.String group, Colossal.UI.Binding.IReader<Game.UI.Widgets.IWidget> pathResolver, Game.UI.Widgets.ValueChangedCallback onValueChanged);
}
```


## Constructors

- `public InvokableBindings()`  

```csharp
public InvokableBindings();
```


## Methods

- `public CreateBindings(System.String group, Colossal.UI.Binding.IReader<Game.UI.Widgets.IWidget> pathResolver, Game.UI.Widgets.ValueChangedCallback onValueChanged) : System.Collections.Generic.IEnumerable<Colossal.UI.Binding.IBinding>`  

```csharp
public IEnumerable<IBinding> CreateBindings(string group, IReader<IWidget> pathResolver, ValueChangedCallback onValueChanged)
	{
		yield return new TriggerBinding<IWidget>(group, "invoke", delegate(IWidget widget)
		{
			if (widget is IInvokable invokable)
			{
				invokable.Invoke();
			}
			else
			{
				UnityEngine.Debug.LogError((widget != null) ? "Widget does not implement IInvokable" : "Invalid widget path");
			}
		}, pathResolver);
	}
```


## Nested types

- `Game.UI.Widgets.InvokableBindings+<>c`  
- `Game.UI.Widgets.InvokableBindings+<CreateBindings>d__0`  

