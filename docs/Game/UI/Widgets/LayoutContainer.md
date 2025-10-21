# Game.UI.Widgets.LayoutContainer

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class abstract public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.IContainerWidget`  

## Code

```csharp
public abstract class LayoutContainer : Game.UI.Widgets.Widget, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.IContainerWidget
{
    private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> m_Children;
    private Game.UI.Widgets.FlexLayout <flex>k__BackingField;

    public Game.UI.Widgets.FlexLayout flex { get; set; }
    public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get; set; }
    public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> visibleChildren { get; }

    protected LayoutContainer();

    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> m_Children`  

```csharp
private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> m_Children;
```

- `private Game.UI.Widgets.FlexLayout <flex>k__BackingField`  

```csharp
private Game.UI.Widgets.FlexLayout <flex>k__BackingField;
```


## Properties

- `public Game.UI.Widgets.FlexLayout flex { get; set }`  

```csharp
public Game.UI.Widgets.FlexLayout flex { get; set; }
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

- `protected LayoutContainer()`  

```csharp
protected LayoutContainer();
```


## Methods

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```


