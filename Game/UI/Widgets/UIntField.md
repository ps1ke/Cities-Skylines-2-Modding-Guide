# Game.UI.Widgets.UIntField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Field<System.UInt32>`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.ISettable`  

## Code

```csharp
public class UIntField : Game.UI.Widgets.Field<System.UInt32>, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.INamed, Game.UI.Widgets.ITooltipTarget, Game.UI.Widgets.IUITagProvider, Game.UI.Widgets.ISettable
{
    private System.UInt32 <min>k__BackingField;
    private System.UInt32 <max>k__BackingField;
    private System.UInt32 <step>k__BackingField;
    private System.UInt32 <stepMultiplier>k__BackingField;

    public System.UInt32 min { get; set; }
    public System.UInt32 max { get; set; }
    public System.UInt32 step { get; set; }
    public System.UInt32 stepMultiplier { get; set; }

    public UIntField();

    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.UInt32 <min>k__BackingField`  

```csharp
private System.UInt32 <min>k__BackingField;
```

- `private System.UInt32 <max>k__BackingField`  

```csharp
private System.UInt32 <max>k__BackingField;
```

- `private System.UInt32 <step>k__BackingField`  

```csharp
private System.UInt32 <step>k__BackingField;
```

- `private System.UInt32 <stepMultiplier>k__BackingField`  

```csharp
private System.UInt32 <stepMultiplier>k__BackingField;
```


## Properties

- `public System.UInt32 min { get; set }`  

```csharp
public System.UInt32 min { get; set; }
```

- `public System.UInt32 max { get; set }`  

```csharp
public System.UInt32 max { get; set; }
```

- `public System.UInt32 step { get; set }`  

```csharp
public System.UInt32 step { get; set; }
```

- `public System.UInt32 stepMultiplier { get; set }`  

```csharp
public System.UInt32 stepMultiplier { get; set; }
```


## Constructors

- `public UIntField()`  

```csharp
public UIntField();
```


## Methods

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected override void WriteProperties(IJsonWriter writer)
	{
		base.WriteProperties(writer);
		writer.PropertyName("min");
		writer.Write(min);
		writer.PropertyName("max");
		writer.Write(max);
		writer.PropertyName("step");
		writer.Write(step);
		writer.PropertyName("stepMultiplier");
		writer.Write(step);
	}
```


