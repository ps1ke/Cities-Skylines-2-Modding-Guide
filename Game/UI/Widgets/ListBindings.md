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
public System.Collections.Generic.IEnumerable<Colossal.UI.Binding.IBinding> CreateBindings(System.String group, Colossal.UI.Binding.IReader<Game.UI.Widgets.IWidget> pathResolver, Game.UI.Widgets.ValueChangedCallback onValueChanged);
```


## Nested types

- `Game.UI.Widgets.ListBindings+<>c__DisplayClass0_0`  
- `Game.UI.Widgets.ListBindings+<CreateBindings>d__0`  

