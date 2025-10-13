# Game.UI.Tooltip.NameTooltip

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`  

## Code

```csharp
public class NameTooltip : Game.UI.Widgets.Widget, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback
{
    private System.String m_Icon;
    public Unity.Entities.Entity m_Entity;
    private Game.UI.NameSystem <nameBinder>k__BackingField;

    public System.String icon { get; set; }
    public Unity.Entities.Entity entity { get; set; }
    public Game.UI.NameSystem nameBinder { get; set; }

    public NameTooltip();

    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.String m_Icon`  

```csharp
private System.String m_Icon;
```

- `public Unity.Entities.Entity m_Entity`  

```csharp
public Unity.Entities.Entity m_Entity;
```

- `private Game.UI.NameSystem <nameBinder>k__BackingField`  

```csharp
private Game.UI.NameSystem <nameBinder>k__BackingField;
```


## Properties

- `public System.String icon { get; set }`  

```csharp
public System.String icon { get; set; }
```

- `public Unity.Entities.Entity entity { get; set }`  

```csharp
public Unity.Entities.Entity entity { get; set; }
```

- `public Game.UI.NameSystem nameBinder { get; set }`  

```csharp
public Game.UI.NameSystem nameBinder { get; set; }
```


## Constructors

- `public NameTooltip()`  

```csharp
public NameTooltip();
```


## Methods

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```


