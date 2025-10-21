# Game.UI.Tooltip.TooltipGroup

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`  

## Code

```csharp
public class TooltipGroup : Game.UI.Widgets.Widget, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback
{
    private Unity.Mathematics.float2 m_Position;
    private Game.UI.Tooltip.TooltipGroup+Category m_Category;
    private Game.UI.Tooltip.TooltipGroup+Alignment m_HorizontalAlignment;
    private Game.UI.Tooltip.TooltipGroup+Alignment m_VerticalAlignment;
    private System.Collections.Generic.List<Game.UI.Widgets.IWidget> m_LastChildren;
    private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> <children>k__BackingField;

    public Unity.Mathematics.float2 position { get; set; }
    public Game.UI.Tooltip.TooltipGroup+Alignment horizontalAlignment { get; set; }
    public Game.UI.Tooltip.TooltipGroup+Alignment verticalAlignment { get; set; }
    public Game.UI.Tooltip.TooltipGroup+Category category { get; set; }
    public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get; set; }
    public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> visibleChildren { get; }

    public TooltipGroup();

    protected virtual Game.UI.Widgets.WidgetChanges Update();
    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private Unity.Mathematics.float2 m_Position`  

```csharp
private Unity.Mathematics.float2 m_Position;
```

- `private Game.UI.Tooltip.TooltipGroup+Category m_Category`  

```csharp
private Game.UI.Tooltip.TooltipGroup+Category m_Category;
```

- `private Game.UI.Tooltip.TooltipGroup+Alignment m_HorizontalAlignment`  

```csharp
private Game.UI.Tooltip.TooltipGroup+Alignment m_HorizontalAlignment;
```

- `private Game.UI.Tooltip.TooltipGroup+Alignment m_VerticalAlignment`  

```csharp
private Game.UI.Tooltip.TooltipGroup+Alignment m_VerticalAlignment;
```

- `private System.Collections.Generic.List<Game.UI.Widgets.IWidget> m_LastChildren`  

```csharp
private System.Collections.Generic.List<Game.UI.Widgets.IWidget> m_LastChildren;
```

- `private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> <children>k__BackingField`  

```csharp
private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> <children>k__BackingField;
```


## Properties

- `public Unity.Mathematics.float2 position { get; set }`  

```csharp
public Unity.Mathematics.float2 position { get; set; }
```

- `public Game.UI.Tooltip.TooltipGroup+Alignment horizontalAlignment { get; set }`  

```csharp
public Game.UI.Tooltip.TooltipGroup+Alignment horizontalAlignment { get; set; }
```

- `public Game.UI.Tooltip.TooltipGroup+Alignment verticalAlignment { get; set }`  

```csharp
public Game.UI.Tooltip.TooltipGroup+Alignment verticalAlignment { get; set; }
```

- `public Game.UI.Tooltip.TooltipGroup+Category category { get; set }`  

```csharp
public Game.UI.Tooltip.TooltipGroup+Category category { get; set; }
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

- `public TooltipGroup()`  

```csharp
public TooltipGroup();
```


## Methods

- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  

```csharp
protected virtual Game.UI.Widgets.WidgetChanges Update();
```

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```


## Nested types

- `Game.UI.Tooltip.TooltipGroup+Alignment`  
- `Game.UI.Tooltip.TooltipGroup+Category`  

