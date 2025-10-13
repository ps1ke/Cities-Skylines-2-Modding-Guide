# Game.UI.Editor.SeasonsField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`  

## Code

```csharp
public class SeasonsField : Game.UI.Widgets.Widget, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback
{
    private Unity.Entities.Entity m_SelectedSeason;
    private System.Collections.Generic.List<Game.Simulation.ClimateSystem+SeasonInfo> m_Seasons;
    private Game.UI.Editor.SeasonsField+SeasonCurves m_SeasonCurves;
    private Game.UI.Editor.SeasonsField+IAdapter <adapter>k__BackingField;

    public Game.UI.Editor.SeasonsField+IAdapter adapter { get; set; }

    public SeasonsField();

    protected virtual Game.UI.Widgets.WidgetChanges Update();
    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private Unity.Entities.Entity m_SelectedSeason`  

```csharp
private Unity.Entities.Entity m_SelectedSeason;
```

- `private System.Collections.Generic.List<Game.Simulation.ClimateSystem+SeasonInfo> m_Seasons`  

```csharp
private System.Collections.Generic.List<Game.Simulation.ClimateSystem+SeasonInfo> m_Seasons;
```

- `private Game.UI.Editor.SeasonsField+SeasonCurves m_SeasonCurves`  

```csharp
private Game.UI.Editor.SeasonsField+SeasonCurves m_SeasonCurves;
```

- `private Game.UI.Editor.SeasonsField+IAdapter <adapter>k__BackingField`  

```csharp
private Game.UI.Editor.SeasonsField+IAdapter <adapter>k__BackingField;
```


## Properties

- `public Game.UI.Editor.SeasonsField+IAdapter adapter { get; set }`  

```csharp
public Game.UI.Editor.SeasonsField+IAdapter adapter { get; set; }
```


## Constructors

- `public SeasonsField()`  

```csharp
public SeasonsField();
```


## Methods

- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  

```csharp
protected override WidgetChanges Update()
	{
		WidgetChanges num = base.Update();
		m_Seasons = adapter.seasons.ToList();
		m_SeasonCurves = adapter.curves;
		return num | WidgetChanges.Properties;
	}
```

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected override void WriteProperties(IJsonWriter writer)
	{
		base.WriteProperties(writer);
		writer.PropertyName("seasons");
		writer.Write((IList<ClimateSystem.SeasonInfo>)m_Seasons);
		writer.PropertyName("curves");
		writer.Write(m_SeasonCurves);
	}
```


## Nested types

- `Game.UI.Editor.SeasonsField+SeasonCurves`  
- `Game.UI.Editor.SeasonsField+Season`  
- `Game.UI.Editor.SeasonsField+IAdapter`  
- `Game.UI.Editor.SeasonsField+Bindings`  

