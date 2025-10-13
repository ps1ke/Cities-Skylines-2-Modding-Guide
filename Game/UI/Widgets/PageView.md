# Game.UI.Widgets.PageView

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.LayoutContainer`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.IContainerWidget`  

## Code

```csharp
public class PageView : Game.UI.Widgets.LayoutContainer, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.IContainerWidget
{
    private System.Int32 m_CurrentPage;

    public System.Int32 currentPage { get; set; }

    public PageView();

    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.Int32 m_CurrentPage`  

```csharp
private System.Int32 m_CurrentPage;
```


## Properties

- `public System.Int32 currentPage { get; set }`  

```csharp
public System.Int32 currentPage { get; set; }
```


## Constructors

- `public PageView()`  

```csharp
public PageView();
```


## Methods

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```


