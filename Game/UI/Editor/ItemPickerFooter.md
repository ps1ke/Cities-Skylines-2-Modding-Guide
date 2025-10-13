# Game.UI.Editor.ItemPickerFooter

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.ISettable`  

## Code

```csharp
public class ItemPickerFooter : Game.UI.Widgets.Widget, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.ISettable
{
    private System.Int32 m_Length;
    private System.Int32 m_ColumnCount;
    private Game.UI.Editor.ItemPickerFooter+IAdapter <adapter>k__BackingField;

    public Game.UI.Editor.ItemPickerFooter+IAdapter adapter { get; set; }
    public System.Boolean shouldTriggerValueChangedEvent { get; }

    public ItemPickerFooter();

    public System.Void SetValue(Colossal.UI.Binding.IJsonReader reader);
    protected virtual Game.UI.Widgets.WidgetChanges Update();
    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.Int32 m_Length`  

```csharp
private System.Int32 m_Length;
```

- `private System.Int32 m_ColumnCount`  

```csharp
private System.Int32 m_ColumnCount;
```

- `private Game.UI.Editor.ItemPickerFooter+IAdapter <adapter>k__BackingField`  

```csharp
private Game.UI.Editor.ItemPickerFooter+IAdapter <adapter>k__BackingField;
```


## Properties

- `public Game.UI.Editor.ItemPickerFooter+IAdapter adapter { get; set }`  

```csharp
public Game.UI.Editor.ItemPickerFooter+IAdapter adapter { get; set; }
```

- `public System.Boolean shouldTriggerValueChangedEvent { get }`  

```csharp
public System.Boolean shouldTriggerValueChangedEvent { get; }
```


## Constructors

- `public ItemPickerFooter()`  

```csharp
public ItemPickerFooter();
```


## Methods

- `public SetValue(Colossal.UI.Binding.IJsonReader reader) : System.Void`  

```csharp
public System.Void SetValue(Colossal.UI.Binding.IJsonReader reader);
```

- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  

```csharp
protected virtual Game.UI.Widgets.WidgetChanges Update();
```

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```


## Nested types

- `Game.UI.Editor.ItemPickerFooter+IAdapter`  

