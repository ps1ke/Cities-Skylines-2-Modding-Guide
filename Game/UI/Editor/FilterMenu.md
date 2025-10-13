# Game.UI.Editor.FilterMenu

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`  

## Code

```csharp
public class FilterMenu : Game.UI.Widgets.Widget, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback
{
    private System.Boolean m_Dirty;
    private Game.UI.Editor.FilterMenu+IAdapter m_Adapter;

    public Game.UI.Editor.FilterMenu+IAdapter adapter { get; set; }

    public FilterMenu();

    private System.Void OnAvailableFiltersChanged();
    private System.Void OnClearFilters();
    private System.Void OnToggleFilter(System.String filter, System.Boolean active);
    protected virtual Game.UI.Widgets.WidgetChanges Update();
    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.Boolean m_Dirty`  

```csharp
private System.Boolean m_Dirty;
```

- `private Game.UI.Editor.FilterMenu+IAdapter m_Adapter`  

```csharp
private Game.UI.Editor.FilterMenu+IAdapter m_Adapter;
```


## Properties

- `public Game.UI.Editor.FilterMenu+IAdapter adapter { get; set }`  

```csharp
public Game.UI.Editor.FilterMenu+IAdapter adapter { get; set; }
```


## Constructors

- `public FilterMenu()`  

```csharp
public FilterMenu();
```


## Methods

- `private OnAvailableFiltersChanged() : System.Void`  

```csharp
private System.Void OnAvailableFiltersChanged();
```

- `private OnClearFilters() : System.Void`  

```csharp
private System.Void OnClearFilters();
```

- `private OnToggleFilter(System.String filter, System.Boolean active) : System.Void`  

```csharp
private System.Void OnToggleFilter(System.String filter, System.Boolean active);
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

- `Game.UI.Editor.FilterMenu+IAdapter`  
- `Game.UI.Editor.FilterMenu+Bindings`  

