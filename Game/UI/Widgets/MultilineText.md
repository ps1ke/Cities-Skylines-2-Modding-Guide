# Game.UI.Widgets.MultilineText

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.NamedWidget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`  

## Code

```csharp
public class MultilineText : Game.UI.Widgets.NamedWidget, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.INamed
{
    private System.String <icon>k__BackingField;

    public System.String icon { get; set; }

    public MultilineText();

    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.String <icon>k__BackingField`  

```csharp
private System.String <icon>k__BackingField;
```


## Properties

- `public System.String icon { get; set }`  

```csharp
public System.String icon { get; set; }
```


## Constructors

- `public MultilineText()`  

```csharp
public MultilineText();
```


## Methods

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected override void WriteProperties(IJsonWriter writer)
	{
		base.WriteProperties(writer);
		writer.PropertyName("icon");
		writer.Write(icon);
	}
```


