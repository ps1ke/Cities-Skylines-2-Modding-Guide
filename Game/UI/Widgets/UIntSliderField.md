# Game.UI.Widgets.UIntSliderField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.UIntField`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.ISettable`  

## Code

```csharp
public class UIntSliderField : Game.UI.Widgets.UIntField, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.INamed, Game.UI.Widgets.ITooltipTarget, Game.UI.Widgets.IUITagProvider, Game.UI.Widgets.ISettable
{
    private System.String <unit>k__BackingField;
    private System.Boolean <scaleDragVolume>k__BackingField;

    public System.String unit { get; set; }
    public System.Boolean scaleDragVolume { get; set; }

    public UIntSliderField();

    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.String <unit>k__BackingField`  

```csharp
private System.String <unit>k__BackingField;
```

- `private System.Boolean <scaleDragVolume>k__BackingField`  

```csharp
private System.Boolean <scaleDragVolume>k__BackingField;
```


## Properties

- `public System.String unit { get; set }`  

```csharp
public System.String unit { get; set; }
```

- `public System.Boolean scaleDragVolume { get; set }`  

```csharp
public System.Boolean scaleDragVolume { get; set; }
```


## Constructors

- `public UIntSliderField()`  

```csharp
public UIntSliderField();
```


## Methods

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```


