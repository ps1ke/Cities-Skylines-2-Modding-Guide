# Game.UI.Editor.ListField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`  

## Code

```csharp
public class ListField : Game.UI.Widgets.Widget, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback
{
    public System.Collections.Generic.List<Game.UI.Editor.ListField+Item> m_Items;
    public System.Action<System.Int32> onItemRemoved;

    public ListField();

    protected System.Void RemoveItem(System.Int32 index);
    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public System.Collections.Generic.List<Game.UI.Editor.ListField+Item> m_Items`  

```csharp
public System.Collections.Generic.List<Game.UI.Editor.ListField+Item> m_Items;
```

- `public System.Action<System.Int32> onItemRemoved`  

```csharp
public System.Action<System.Int32> onItemRemoved;
```


## Constructors

- `public ListField()`  

```csharp
public ListField();
```


## Methods

- `protected RemoveItem(System.Int32 index) : System.Void`  

```csharp
protected System.Void RemoveItem(System.Int32 index);
```

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```


## Nested types

- `Game.UI.Editor.ListField+Item`  
- `Game.UI.Editor.ListField+Bindings`  

