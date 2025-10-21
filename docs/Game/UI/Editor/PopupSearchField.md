# Game.UI.Editor.PopupSearchField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.ISettable`  

## Code

```csharp
public class PopupSearchField : Game.UI.Widgets.Widget, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.ISettable
{
    private System.String m_Value;
    private System.Boolean m_ValueIsFavorite;
    private System.Collections.Generic.List<Game.UI.Editor.PopupSearchField+Suggestion> m_Suggestions;
    private Game.UI.Editor.PopupSearchField+IAdapter <adapter>k__BackingField;
    private System.Boolean <hasFavorites>k__BackingField;

    public Game.UI.Editor.PopupSearchField+IAdapter adapter { get; set; }
    public System.Boolean hasFavorites { get; set; }
    public System.Boolean shouldTriggerValueChangedEvent { get; }

    public PopupSearchField();

    public System.Void SetValue(Colossal.UI.Binding.IJsonReader reader);
    public System.Void SetValue(System.String value);
    protected virtual Game.UI.Widgets.WidgetChanges Update();
    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.String m_Value`  

```csharp
private System.String m_Value;
```

- `private System.Boolean m_ValueIsFavorite`  

```csharp
private System.Boolean m_ValueIsFavorite;
```

- `private System.Collections.Generic.List<Game.UI.Editor.PopupSearchField+Suggestion> m_Suggestions`  

```csharp
private System.Collections.Generic.List<Game.UI.Editor.PopupSearchField+Suggestion> m_Suggestions;
```

- `private Game.UI.Editor.PopupSearchField+IAdapter <adapter>k__BackingField`  

```csharp
private Game.UI.Editor.PopupSearchField+IAdapter <adapter>k__BackingField;
```

- `private System.Boolean <hasFavorites>k__BackingField`  

```csharp
private System.Boolean <hasFavorites>k__BackingField;
```


## Properties

- `public Game.UI.Editor.PopupSearchField+IAdapter adapter { get; set }`  

```csharp
public Game.UI.Editor.PopupSearchField+IAdapter adapter { get; set; }
```

- `public System.Boolean hasFavorites { get; set }`  

```csharp
public System.Boolean hasFavorites { get; set; }
```

- `public System.Boolean shouldTriggerValueChangedEvent { get }`  

```csharp
public System.Boolean shouldTriggerValueChangedEvent { get; }
```


## Constructors

- `public PopupSearchField()`  

```csharp
public PopupSearchField();
```


## Methods

- `public SetValue(Colossal.UI.Binding.IJsonReader reader) : System.Void`  

```csharp
public System.Void SetValue(Colossal.UI.Binding.IJsonReader reader);
```

- `public SetValue(System.String value) : System.Void`  

```csharp
public System.Void SetValue(System.String value);
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

- `Game.UI.Editor.PopupSearchField+IAdapter`  
- `Game.UI.Editor.PopupSearchField+Suggestion`  
- `Game.UI.Editor.PopupSearchField+Bindings`  

