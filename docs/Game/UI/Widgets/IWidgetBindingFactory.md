# Game.UI.Widgets.IWidgetBindingFactory

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IWidgetBindingFactory
{
    public abstract System.Collections.Generic.IEnumerable<Colossal.UI.Binding.IBinding> CreateBindings(System.String group, Colossal.UI.Binding.IReader<Game.UI.Widgets.IWidget> pathResolver, Game.UI.Widgets.ValueChangedCallback onValueChanged);
}
```


## Methods

- `public abstract CreateBindings(System.String group, Colossal.UI.Binding.IReader<Game.UI.Widgets.IWidget> pathResolver, Game.UI.Widgets.ValueChangedCallback onValueChanged) : System.Collections.Generic.IEnumerable<Colossal.UI.Binding.IBinding>`  

```csharp
public abstract System.Collections.Generic.IEnumerable<Colossal.UI.Binding.IBinding> CreateBindings(System.String group, Colossal.UI.Binding.IReader<Game.UI.Widgets.IWidget> pathResolver, Game.UI.Widgets.ValueChangedCallback onValueChanged);
```


