# Game.UI.Tooltip.ZoningEvaluationTooltip

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`  

## Code

```csharp
public class ZoningEvaluationTooltip : Game.UI.Widgets.Widget, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback
{
    private Game.Simulation.ZoneEvaluationUtils+ZoningEvaluationFactor m_Factor;
    private System.Single m_Score;

    public Game.Simulation.ZoneEvaluationUtils+ZoningEvaluationFactor factor { get; set; }
    public System.Single score { get; set; }

    public ZoningEvaluationTooltip();

    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private Game.Simulation.ZoneEvaluationUtils+ZoningEvaluationFactor m_Factor`  

```csharp
private Game.Simulation.ZoneEvaluationUtils+ZoningEvaluationFactor m_Factor;
```

- `private System.Single m_Score`  

```csharp
private System.Single m_Score;
```


## Properties

- `public Game.Simulation.ZoneEvaluationUtils+ZoningEvaluationFactor factor { get; set }`  

```csharp
public Game.Simulation.ZoneEvaluationUtils+ZoningEvaluationFactor factor { get; set; }
```

- `public System.Single score { get; set }`  

```csharp
public System.Single score { get; set; }
```


## Constructors

- `public ZoningEvaluationTooltip()`  

```csharp
public ZoningEvaluationTooltip();
```


## Methods

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```


