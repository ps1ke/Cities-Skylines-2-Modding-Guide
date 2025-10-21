# Game.UI.Tooltip.TempWaterPumpingTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TempWaterPumpingTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Unity.Entities.EntityQuery m_ErrorQuery;
    private Unity.Entities.EntityQuery m_TempQuery;
    private Unity.Entities.EntityQuery m_PumpQuery;
    private Unity.Entities.EntityQuery m_ParameterQuery;
    private Game.UI.Tooltip.ProgressTooltip m_Capacity;
    private Game.UI.Tooltip.IntTooltip m_ReservoirUsage;
    private Game.UI.Tooltip.StringTooltip m_OverRefreshCapacityWarning;
    private Game.UI.Tooltip.StringTooltip m_AvailabilityWarning;
    private Game.UI.Localization.LocalizedString m_GroundWarning;
    private Game.UI.Localization.LocalizedString m_SurfaceWarning;
    private Unity.Collections.NativeReference<Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TempResult> m_TempResult;
    private Unity.Collections.NativeReference<Game.UI.Tooltip.TempWaterPumpingTooltipSystem+GroundWaterReservoirResult> m_ReservoirResult;
    private Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TypeHandle __TypeHandle;

    public TempWaterPumpingTooltipSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    private System.Void ProcessAvailabilityWarning(Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TempResult temp, Game.UI.Localization.LocalizedString warningText);
    private System.Void ProcessProduction(Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TempResult temp);
    private System.Void ProcessReservoir(Game.UI.Tooltip.TempWaterPumpingTooltipSystem+GroundWaterReservoirResult reservoir);
    private System.Void ProcessResults();
}
```


## Fields

- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  

```csharp
private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Unity.Entities.EntityQuery m_ErrorQuery`  

```csharp
private Unity.Entities.EntityQuery m_ErrorQuery;
```

- `private Unity.Entities.EntityQuery m_TempQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempQuery;
```

- `private Unity.Entities.EntityQuery m_PumpQuery`  

```csharp
private Unity.Entities.EntityQuery m_PumpQuery;
```

- `private Unity.Entities.EntityQuery m_ParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_ParameterQuery;
```

- `private Game.UI.Tooltip.ProgressTooltip m_Capacity`  

```csharp
private Game.UI.Tooltip.ProgressTooltip m_Capacity;
```

- `private Game.UI.Tooltip.IntTooltip m_ReservoirUsage`  

```csharp
private Game.UI.Tooltip.IntTooltip m_ReservoirUsage;
```

- `private Game.UI.Tooltip.StringTooltip m_OverRefreshCapacityWarning`  

```csharp
private Game.UI.Tooltip.StringTooltip m_OverRefreshCapacityWarning;
```

- `private Game.UI.Tooltip.StringTooltip m_AvailabilityWarning`  

```csharp
private Game.UI.Tooltip.StringTooltip m_AvailabilityWarning;
```

- `private Game.UI.Localization.LocalizedString m_GroundWarning`  

```csharp
private Game.UI.Localization.LocalizedString m_GroundWarning;
```

- `private Game.UI.Localization.LocalizedString m_SurfaceWarning`  

```csharp
private Game.UI.Localization.LocalizedString m_SurfaceWarning;
```

- `private Unity.Collections.NativeReference<Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TempResult> m_TempResult`  

```csharp
private Unity.Collections.NativeReference<Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TempResult> m_TempResult;
```

- `private Unity.Collections.NativeReference<Game.UI.Tooltip.TempWaterPumpingTooltipSystem+GroundWaterReservoirResult> m_ReservoirResult`  

```csharp
private Unity.Collections.NativeReference<Game.UI.Tooltip.TempWaterPumpingTooltipSystem+GroundWaterReservoirResult> m_ReservoirResult;
```

- `private Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TempWaterPumpingTooltipSystem()`  

```csharp
public TempWaterPumpingTooltipSystem();
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

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private ProcessAvailabilityWarning(Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TempResult temp, Game.UI.Localization.LocalizedString warningText) : System.Void`  

```csharp
private System.Void ProcessAvailabilityWarning(Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TempResult temp, Game.UI.Localization.LocalizedString warningText);
```

- `private ProcessProduction(Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TempResult temp) : System.Void`  

```csharp
private System.Void ProcessProduction(Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TempResult temp);
```

- `private ProcessReservoir(Game.UI.Tooltip.TempWaterPumpingTooltipSystem+GroundWaterReservoirResult reservoir) : System.Void`  

```csharp
private System.Void ProcessReservoir(Game.UI.Tooltip.TempWaterPumpingTooltipSystem+GroundWaterReservoirResult reservoir);
```

- `private ProcessResults() : System.Void`  

```csharp
private System.Void ProcessResults();
```


## Nested types

- `Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TempResult`  
- `Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TempJob`  
- `Game.UI.Tooltip.TempWaterPumpingTooltipSystem+GroundWaterPumpJob`  
- `Game.UI.Tooltip.TempWaterPumpingTooltipSystem+GroundWaterReservoirResult`  
- `Game.UI.Tooltip.TempWaterPumpingTooltipSystem+GroundWaterReservoirJob`  
- `Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TypeHandle`  

