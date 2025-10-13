# Game.UI.Widgets.IconButtonGroup

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`  

## Code

```csharp
public class IconButtonGroup : Game.UI.Widgets.Widget, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback
{
    private Game.UI.Widgets.IconButton[] m_Children;

    public Game.UI.Widgets.IconButton[] children { get; set; }
    public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> visibleChildren { get; }

    public IconButtonGroup();

    public static Game.UI.Widgets.IconButtonGroup WithChildren(Game.UI.Widgets.IconButton[] children);
}
```


## Fields

- `private Game.UI.Widgets.IconButton[] m_Children`  

```csharp
private Game.UI.Widgets.IconButton[] m_Children;
```


## Properties

- `public Game.UI.Widgets.IconButton[] children { get; set }`  

```csharp
public Game.UI.Widgets.IconButton[] children { get; set; }
```

- `public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> visibleChildren { get }`  

```csharp
public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> visibleChildren { get; }
```


## Constructors

- `public IconButtonGroup()`  

```csharp
public IconButtonGroup();
```


## Methods

- `public static WithChildren(Game.UI.Widgets.IconButton[] children) : Game.UI.Widgets.IconButtonGroup`  

```csharp
public static Game.UI.Widgets.IconButtonGroup WithChildren(Game.UI.Widgets.IconButton[] children);
```


