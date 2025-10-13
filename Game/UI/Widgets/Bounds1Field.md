# Game.UI.Widgets.Bounds1Field

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class abstract public  

**Base:** `Game.UI.Widgets.Field<Colossal.Mathematics.Bounds1>`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.ISettable`  

## Code

```csharp
public abstract class Bounds1Field : Game.UI.Widgets.Field<Colossal.Mathematics.Bounds1>, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.INamed, Game.UI.Widgets.ITooltipTarget, Game.UI.Widgets.IUITagProvider, Game.UI.Widgets.ISettable
{
    private System.Single <min>k__BackingField;
    private System.Single <max>k__BackingField;
    private System.Int32 <fractionDigits>k__BackingField;
    private System.Single <step>k__BackingField;
    private System.Boolean <allowMinGreaterMax>k__BackingField;

    public System.Single min { get; set; }
    public System.Single max { get; set; }
    public System.Int32 fractionDigits { get; set; }
    public System.Single step { get; set; }
    public System.Boolean allowMinGreaterMax { get; set; }

    protected Bounds1Field();

    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.Single <min>k__BackingField`  

```csharp
private System.Single <min>k__BackingField;
```

- `private System.Single <max>k__BackingField`  

```csharp
private System.Single <max>k__BackingField;
```

- `private System.Int32 <fractionDigits>k__BackingField`  

```csharp
private System.Int32 <fractionDigits>k__BackingField;
```

- `private System.Single <step>k__BackingField`  

```csharp
private System.Single <step>k__BackingField;
```

- `private System.Boolean <allowMinGreaterMax>k__BackingField`  

```csharp
private System.Boolean <allowMinGreaterMax>k__BackingField;
```


## Properties

- `public System.Single min { get; set }`  

```csharp
public System.Single min { get; set; }
```

- `public System.Single max { get; set }`  

```csharp
public System.Single max { get; set; }
```

- `public System.Int32 fractionDigits { get; set }`  

```csharp
public System.Int32 fractionDigits { get; set; }
```

- `public System.Single step { get; set }`  

```csharp
public System.Single step { get; set; }
```

- `public System.Boolean allowMinGreaterMax { get; set }`  

```csharp
public System.Boolean allowMinGreaterMax { get; set; }
```


## Constructors

- `protected Bounds1Field()`  

```csharp
protected Bounds1Field();
```


## Methods

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```


