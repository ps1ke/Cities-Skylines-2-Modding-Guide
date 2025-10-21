# Game.UI.Widgets.ButtonRow

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`  

## Code

```csharp
public class ButtonRow : Game.UI.Widgets.Widget, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback
{
    private Game.UI.Widgets.Button[] m_Children;

    public Game.UI.Widgets.Button[] children { get; set; }
    public System.Boolean isVisible { get; }
    public System.Boolean isActive { get; }
    public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> visibleChildren { get; }

    public ButtonRow();

    public virtual Game.UI.Widgets.WidgetChanges UpdateVisibility();
    public static Game.UI.Widgets.ButtonRow WithChildren(Game.UI.Widgets.Button[] children);
}
```


## Fields

- `private Game.UI.Widgets.Button[] m_Children`  

```csharp
private Game.UI.Widgets.Button[] m_Children;
```


## Properties

- `public Game.UI.Widgets.Button[] children { get; set }`  

```csharp
public Game.UI.Widgets.Button[] children { get; set; }
```

- `public System.Boolean isVisible { get }`  

```csharp
public System.Boolean isVisible { get; }
```

- `public System.Boolean isActive { get }`  

```csharp
public System.Boolean isActive { get; }
```

- `public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> visibleChildren { get }`  

```csharp
public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> visibleChildren { get; }
```


## Constructors

- `public ButtonRow()`  

```csharp
public ButtonRow();
```


## Methods

- `public virtual UpdateVisibility() : Game.UI.Widgets.WidgetChanges`  

```csharp
public virtual Game.UI.Widgets.WidgetChanges UpdateVisibility();
```

- `public static WithChildren(Game.UI.Widgets.Button[] children) : Game.UI.Widgets.ButtonRow`  

```csharp
public static Game.UI.Widgets.ButtonRow WithChildren(Game.UI.Widgets.Button[] children);
```


## Nested types

- `Game.UI.Widgets.ButtonRow+<>c`  

