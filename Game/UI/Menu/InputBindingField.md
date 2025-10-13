# Game.UI.Menu.InputBindingField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Field<Game.Input.ProxyBinding>`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.ISettable`, `Game.UI.Widgets.IWarning`  

## Code

```csharp
public class InputBindingField : Game.UI.Widgets.Field<Game.Input.ProxyBinding>, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.INamed, Game.UI.Widgets.ITooltipTarget, Game.UI.Widgets.IUITagProvider, Game.UI.Widgets.ISettable, Game.UI.Widgets.IWarning
{
    public System.Boolean warning { get; set; }

    public InputBindingField();

    protected virtual System.Boolean ValueEquals(Game.Input.ProxyBinding newValue, Game.Input.ProxyBinding oldValue);
    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Properties

- `public System.Boolean warning { get; set }`  

```csharp
public System.Boolean warning { get; set; }
```


## Constructors

- `public InputBindingField()`  

```csharp
public InputBindingField()
	{
		base.valueWriter = new ValueWriter<ProxyBinding>();
	}
```


## Methods

- `protected virtual ValueEquals(Game.Input.ProxyBinding newValue, Game.Input.ProxyBinding oldValue) : System.Boolean`  

```csharp
protected override bool ValueEquals(ProxyBinding newValue, ProxyBinding oldValue)
	{
		return ProxyBinding.pathAndModifiersComparer.Equals(newValue, oldValue);
	}
```

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected override void WriteProperties(IJsonWriter writer)
	{
		base.WriteProperties(writer);
		writer.PropertyName("conflicts");
		writer.Write(m_Value.conflicts);
	}
```


## Nested types

- `Game.UI.Menu.InputBindingField+Bindings`  

