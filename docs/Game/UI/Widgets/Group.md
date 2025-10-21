# Game.UI.Widgets.Group

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.NamedWidgetWithTooltip`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.IContainerWidget`  

## Code

```csharp
public class Group : Game.UI.Widgets.NamedWidgetWithTooltip, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.INamed, Game.UI.Widgets.ITooltipTarget, Game.UI.Widgets.IUITagProvider, Game.UI.Widgets.IContainerWidget
{
    private Game.UI.Widgets.Group+TooltipPosition <tooltipPos>k__BackingField;
    private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> m_Children;

    public Game.UI.Widgets.Group+TooltipPosition tooltipPos { get; set; }
    public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get; set; }
    public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> visibleChildren { get; }

    public Group();

    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private Game.UI.Widgets.Group+TooltipPosition <tooltipPos>k__BackingField`  

```csharp
private Game.UI.Widgets.Group+TooltipPosition <tooltipPos>k__BackingField;
```

- `private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> m_Children`  

```csharp
private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> m_Children;
```


## Properties

- `public Game.UI.Widgets.Group+TooltipPosition tooltipPos { get; set }`  

```csharp
public Game.UI.Widgets.Group+TooltipPosition tooltipPos { get; set; }
```

- `public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get; set }`  

```csharp
public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get; set; }
```

- `public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> visibleChildren { get }`  

```csharp
public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> visibleChildren { get; }
```


## Constructors

- `public Group()`  

```csharp
public Group();
```


## Methods

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```


## Nested types

- `Game.UI.Widgets.Group+TooltipPosition`  

