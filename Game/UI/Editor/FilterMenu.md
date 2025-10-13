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
private void OnAvailableFiltersChanged()
	{
		m_Dirty = true;
	}
```

- `private OnClearFilters() : System.Void`  

```csharp
private void OnClearFilters()
	{
		adapter.ClearFilters();
		m_Dirty = true;
	}
```

- `private OnToggleFilter(System.String filter, System.Boolean active) : System.Void`  

```csharp
private void OnToggleFilter(string filter, bool active)
	{
		adapter.ToggleFilter(filter, active);
		m_Dirty = true;
	}
```

- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  

```csharp
protected override WidgetChanges Update()
	{
		WidgetChanges widgetChanges = base.Update();
		if (m_Dirty)
		{
			widgetChanges |= WidgetChanges.Properties;
		}
		m_Dirty = false;
		return widgetChanges;
	}
```

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected override void WriteProperties(IJsonWriter writer)
	{
		base.WriteProperties(writer);
		writer.PropertyName("availableFilters");
		writer.Write((IList<string>)adapter.availableFilters);
		writer.PropertyName("activeFilters");
		writer.Write((IList<string>)adapter.activeFilters);
	}
```


## Nested types

- `Game.UI.Editor.FilterMenu+IAdapter`  
- `Game.UI.Editor.FilterMenu+Bindings`  

