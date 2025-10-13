# Game.UI.Editor.ErrorLabel

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Label`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`  

## Code

```csharp
public class ErrorLabel : Game.UI.Widgets.Label, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.INamed, Game.UI.Widgets.ITooltipTarget, Game.UI.Widgets.IUITagProvider
{
    private System.Boolean m_Visible;

    public System.Boolean visible { get; set; }

    public ErrorLabel();

    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.Boolean m_Visible`  

```csharp
private System.Boolean m_Visible;
```


## Properties

- `public System.Boolean visible { get; set }`  

```csharp
public System.Boolean visible { get; set; }
```


## Constructors

- `public ErrorLabel()`  

```csharp
public ErrorLabel();
```


## Methods

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected override void WriteProperties(IJsonWriter writer)
	{
		base.WriteProperties(writer);
		writer.PropertyName("visible");
		writer.Write(m_Visible);
	}
```


