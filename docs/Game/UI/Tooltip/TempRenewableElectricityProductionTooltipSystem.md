# Game.UI.Tooltip.TempRenewableElectricityProductionTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TempRenewableElectricityProductionTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.Simulation.WindSystem m_WindSystem;
    private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
    private Unity.Entities.EntityQuery m_ErrorQuery;
    private Unity.Entities.EntityQuery m_TempQuery;
    private Game.UI.Tooltip.ProgressTooltip m_Production;
    private Game.UI.Tooltip.StringTooltip m_WindWarning;
    private Game.UI.Tooltip.StringTooltip m_GroundWaterAvailabilityWarning;
    private Game.UI.Tooltip.TempRenewableElectricityProductionTooltipSystem+TypeHandle __TypeHandle;

    public TempRenewableElectricityProductionTooltipSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.WindSystem m_WindSystem`  

```csharp
private Game.Simulation.WindSystem m_WindSystem;
```

- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  

```csharp
private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
```

- `private Unity.Entities.EntityQuery m_ErrorQuery`  

```csharp
private Unity.Entities.EntityQuery m_ErrorQuery;
```

- `private Unity.Entities.EntityQuery m_TempQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempQuery;
```

- `private Game.UI.Tooltip.ProgressTooltip m_Production`  

```csharp
private Game.UI.Tooltip.ProgressTooltip m_Production;
```

- `private Game.UI.Tooltip.StringTooltip m_WindWarning`  

```csharp
private Game.UI.Tooltip.StringTooltip m_WindWarning;
```

- `private Game.UI.Tooltip.StringTooltip m_GroundWaterAvailabilityWarning`  

```csharp
private Game.UI.Tooltip.StringTooltip m_GroundWaterAvailabilityWarning;
```

- `private Game.UI.Tooltip.TempRenewableElectricityProductionTooltipSystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.Tooltip.TempRenewableElectricityProductionTooltipSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TempRenewableElectricityProductionTooltipSystem()`  

```csharp
public TempRenewableElectricityProductionTooltipSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.UI.Tooltip.TempRenewableElectricityProductionTooltipSystem+TypeHandle`  

