# Game.UI.Widgets.IntSliderField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.IntField<System.Int32>`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.ISettable`, `Game.UI.Widgets.IWarning`  

## Code

```csharp
public class IntSliderField : Game.UI.Widgets.IntField<System.Int32>, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.INamed, Game.UI.Widgets.ITooltipTarget, Game.UI.Widgets.IUITagProvider, Game.UI.Widgets.ISettable, Game.UI.Widgets.IWarning
{
    private System.Boolean m_Warning;
    private System.Func<System.Boolean> <warningAction>k__BackingField;
    private System.String <unit>k__BackingField;
    private System.Boolean <signed>k__BackingField;
    private System.Boolean <separateThousands>k__BackingField;
    private System.Boolean <scaleDragVolume>k__BackingField;
    private System.Boolean <updateOnDragEnd>k__BackingField;

    public System.Func<System.Boolean> warningAction { get; set; }
    public System.String unit { get; set; }
    public System.Boolean signed { get; set; }
    public System.Boolean separateThousands { get; set; }
    public System.Boolean scaleDragVolume { get; set; }
    public System.Boolean updateOnDragEnd { get; set; }
    public System.Boolean warning { get; set; }

    public IntSliderField();

    protected virtual Game.UI.Widgets.WidgetChanges Update();
    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.Boolean m_Warning`  

```csharp
private System.Boolean m_Warning;
```

- `private System.Func<System.Boolean> <warningAction>k__BackingField`  

```csharp
private System.Func<System.Boolean> <warningAction>k__BackingField;
```

- `private System.String <unit>k__BackingField`  

```csharp
private System.String <unit>k__BackingField;
```

- `private System.Boolean <signed>k__BackingField`  

```csharp
private System.Boolean <signed>k__BackingField;
```

- `private System.Boolean <separateThousands>k__BackingField`  

```csharp
private System.Boolean <separateThousands>k__BackingField;
```

- `private System.Boolean <scaleDragVolume>k__BackingField`  

```csharp
private System.Boolean <scaleDragVolume>k__BackingField;
```

- `private System.Boolean <updateOnDragEnd>k__BackingField`  

```csharp
private System.Boolean <updateOnDragEnd>k__BackingField;
```


## Properties

- `public System.Func<System.Boolean> warningAction { get; set }`  

```csharp
public System.Func<System.Boolean> warningAction { get; set; }
```

- `public System.String unit { get; set }`  

```csharp
public System.String unit { get; set; }
```

- `public System.Boolean signed { get; set }`  

```csharp
public System.Boolean signed { get; set; }
```

- `public System.Boolean separateThousands { get; set }`  

```csharp
public System.Boolean separateThousands { get; set; }
```

- `public System.Boolean scaleDragVolume { get; set }`  

```csharp
public System.Boolean scaleDragVolume { get; set; }
```

- `public System.Boolean updateOnDragEnd { get; set }`  

```csharp
public System.Boolean updateOnDragEnd { get; set; }
```

- `public System.Boolean warning { get; set }`  

```csharp
public System.Boolean warning { get; set; }
```


## Constructors

- `public IntSliderField()`  

```csharp
public IntSliderField();
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


