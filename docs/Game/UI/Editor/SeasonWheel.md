# Game.UI.Editor.SeasonWheel

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`  

## Code

```csharp
public class SeasonWheel : Game.UI.Widgets.Widget, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback
{
    private Unity.Entities.Entity m_SelectedSeason;
    private System.Collections.Generic.List<Game.UI.Editor.SeasonWheel+Season> m_Seasons;
    private Game.UI.Editor.SeasonWheel+IAdapter <adapter>k__BackingField;

    public Game.UI.Editor.SeasonWheel+IAdapter adapter { get; set; }

    public SeasonWheel();

    protected virtual Game.UI.Widgets.WidgetChanges Update();
    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private Unity.Entities.Entity m_SelectedSeason`  

```csharp
private Unity.Entities.Entity m_SelectedSeason;
```

- `private System.Collections.Generic.List<Game.UI.Editor.SeasonWheel+Season> m_Seasons`  

```csharp
private System.Collections.Generic.List<Game.UI.Editor.SeasonWheel+Season> m_Seasons;
```

- `private Game.UI.Editor.SeasonWheel+IAdapter <adapter>k__BackingField`  

```csharp
private Game.UI.Editor.SeasonWheel+IAdapter <adapter>k__BackingField;
```


## Properties

- `public Game.UI.Editor.SeasonWheel+IAdapter adapter { get; set }`  

```csharp
public Game.UI.Editor.SeasonWheel+IAdapter adapter { get; set; }
```


## Constructors

- `public SeasonWheel()`  

```csharp
public SeasonWheel();
```


## Methods

- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  

```csharp
protected virtual Game.UI.Widgets.WidgetChanges Update();
```

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```


## Nested types

- `Game.UI.Editor.SeasonWheel+Season`  
- `Game.UI.Editor.SeasonWheel+IAdapter`  
- `Game.UI.Editor.SeasonWheel+Bindings`  

