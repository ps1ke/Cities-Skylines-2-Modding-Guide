# Game.UI.Widgets.RangedSliderField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.FloatSliderField<System.Single>`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.ISettable`, `Game.UI.Widgets.IIconProvider`  

## Code

```csharp
public class RangedSliderField : Game.UI.Widgets.FloatSliderField<System.Single>, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.INamed, Game.UI.Widgets.ITooltipTarget, Game.UI.Widgets.IUITagProvider, Game.UI.Widgets.ISettable, Game.UI.Widgets.IIconProvider
{
    private System.Single[] <ranges>k__BackingField;
    private System.Func<System.String> <iconSrc>k__BackingField;

    protected System.Single defaultMin { protected get; }
    protected System.Single defaultMax { protected get; }
    public System.Single[] ranges { get; set; }
    public System.Func<System.String> iconSrc { get; set; }

    public RangedSliderField();

    public virtual System.Single ToFieldType(Unity.Mathematics.double4 value);
    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.Single[] <ranges>k__BackingField`  

```csharp
private System.Single[] <ranges>k__BackingField;
```

- `private System.Func<System.String> <iconSrc>k__BackingField`  

```csharp
private System.Func<System.String> <iconSrc>k__BackingField;
```


## Properties

- `protected System.Single defaultMin { protected get }`  

```csharp
protected System.Single defaultMin { protected get; }
```

- `protected System.Single defaultMax { protected get }`  

```csharp
protected System.Single defaultMax { protected get; }
```

- `public System.Single[] ranges { get; set }`  

```csharp
public System.Single[] ranges { get; set; }
```

- `public System.Func<System.String> iconSrc { get; set }`  

```csharp
public System.Func<System.String> iconSrc { get; set; }
```


## Constructors

- `public RangedSliderField()`  

```csharp
public RangedSliderField();
```


## Methods

- `public virtual ToFieldType(Unity.Mathematics.double4 value) : System.Single`  

```csharp
public virtual System.Single ToFieldType(Unity.Mathematics.double4 value);
```

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```


