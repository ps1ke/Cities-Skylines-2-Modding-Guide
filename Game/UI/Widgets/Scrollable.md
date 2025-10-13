# Game.UI.Widgets.Scrollable

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.LayoutContainer`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.IContainerWidget`  

## Code

```csharp
public class Scrollable : Game.UI.Widgets.LayoutContainer, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.IContainerWidget
{
    private Game.UI.Widgets.Direction <direction>k__BackingField;

    public Game.UI.Widgets.Direction direction { get; set; }

    public Scrollable();

    public static Game.UI.Widgets.Scrollable WithChildren(System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children);
    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private Game.UI.Widgets.Direction <direction>k__BackingField`  

```csharp
private Game.UI.Widgets.Direction <direction>k__BackingField;
```


## Properties

- `public Game.UI.Widgets.Direction direction { get; set }`  

```csharp
public Game.UI.Widgets.Direction direction { get; set; }
```


## Constructors

- `public Scrollable()`  

```csharp
public Scrollable();
```


## Methods

- `public static WithChildren(System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children) : Game.UI.Widgets.Scrollable`  

```csharp
public static Game.UI.Widgets.Scrollable WithChildren(System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children);
```

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```


