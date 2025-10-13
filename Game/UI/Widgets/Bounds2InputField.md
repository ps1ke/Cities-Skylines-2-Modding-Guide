# Game.UI.Widgets.Bounds2InputField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Field<Colossal.Mathematics.Bounds2>`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.ISettable`  

## Code

```csharp
public class Bounds2InputField : Game.UI.Widgets.Field<Colossal.Mathematics.Bounds2>, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.INamed, Game.UI.Widgets.ITooltipTarget, Game.UI.Widgets.IUITagProvider, Game.UI.Widgets.ISettable
{
    private System.Boolean <allowMinGreaterMax>k__BackingField;

    public System.Boolean allowMinGreaterMax { get; set; }

    public Bounds2InputField();

    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.Boolean <allowMinGreaterMax>k__BackingField`  

```csharp
private System.Boolean <allowMinGreaterMax>k__BackingField;
```


## Properties

- `public System.Boolean allowMinGreaterMax { get; set }`  

```csharp
public System.Boolean allowMinGreaterMax { get; set; }
```


## Constructors

- `public Bounds2InputField()`  

```csharp
public Bounds2InputField();
```


## Methods

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected override void WriteProperties(IJsonWriter writer)
	{
		base.WriteProperties(writer);
		writer.PropertyName("allowMinGreaterMax");
		writer.Write(allowMinGreaterMax);
	}
```


