# Game.UI.Debug.Image

**Assembly:** `Game`  
**Namespace:** `Game.UI.Debug`  

**Type:** class public  

**Base:** `Game.UI.Widgets.NamedWidget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`  

## Code

```csharp
public class Image : Game.UI.Widgets.NamedWidget, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.INamed
{
    private System.String m_Uri;

    public System.String uri { get; set; }

    public Image();

    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.String m_Uri`  

```csharp
private System.String m_Uri;
```


## Properties

- `public System.String uri { get; set }`  

```csharp
public System.String uri { get; set; }
```


## Constructors

- `public Image()`  

```csharp
public Image();
```


## Methods

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```


