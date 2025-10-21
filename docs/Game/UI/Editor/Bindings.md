# Game.UI.Editor.SeasonWheel+Bindings

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Widgets.IWidgetBindingFactory`  

## Code

```csharp
public class Bindings : Game.UI.Widgets.IWidgetBindingFactory
{
    public Bindings();

    public System.Collections.Generic.IEnumerable<Colossal.UI.Binding.IBinding> CreateBindings(System.String group, Colossal.UI.Binding.IReader<Game.UI.Widgets.IWidget> pathResolver, Game.UI.Widgets.ValueChangedCallback onValueChanged);
}
```


## Constructors

- `public Bindings()`  

```csharp
public Bindings();
```


## Methods

- `public CreateBindings(System.String group, Colossal.UI.Binding.IReader<Game.UI.Widgets.IWidget> pathResolver, Game.UI.Widgets.ValueChangedCallback onValueChanged) : System.Collections.Generic.IEnumerable<Colossal.UI.Binding.IBinding>`  

```csharp
public System.Collections.Generic.IEnumerable<Colossal.UI.Binding.IBinding> CreateBindings(System.String group, Colossal.UI.Binding.IReader<Game.UI.Widgets.IWidget> pathResolver, Game.UI.Widgets.ValueChangedCallback onValueChanged);
```


## Nested types

- `Game.UI.Editor.SeasonWheel+Bindings+<>c`  
- `Game.UI.Editor.SeasonWheel+Bindings+<>c__DisplayClass0_0`  
- `Game.UI.Editor.SeasonWheel+Bindings+<CreateBindings>d__0`  

