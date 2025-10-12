# Game.UI.Tooltip.TempWaterPumpingTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  
- `private Game.Simulation.WaterSystem m_WaterSystem`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Unity.Entities.EntityQuery m_ErrorQuery`  
- `private Unity.Entities.EntityQuery m_TempQuery`  
- `private Unity.Entities.EntityQuery m_PumpQuery`  
- `private Unity.Entities.EntityQuery m_ParameterQuery`  
- `private Game.UI.Tooltip.ProgressTooltip m_Capacity`  
- `private Game.UI.Tooltip.IntTooltip m_ReservoirUsage`  
- `private Game.UI.Tooltip.StringTooltip m_OverRefreshCapacityWarning`  
- `private Game.UI.Tooltip.StringTooltip m_AvailabilityWarning`  
- `private Game.UI.Localization.LocalizedString m_GroundWarning`  
- `private Game.UI.Localization.LocalizedString m_SurfaceWarning`  
- `private Unity.Collections.NativeReference<Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TempResult> m_TempResult`  
- `private Unity.Collections.NativeReference<Game.UI.Tooltip.TempWaterPumpingTooltipSystem+GroundWaterReservoirResult> m_ReservoirResult`  
- `private Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TypeHandle __TypeHandle`  

## Constructors

- `public TempWaterPumpingTooltipSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private ProcessAvailabilityWarning(Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TempResult temp, Game.UI.Localization.LocalizedString warningText) : System.Void`  
- `private ProcessProduction(Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TempResult temp) : System.Void`  
- `private ProcessReservoir(Game.UI.Tooltip.TempWaterPumpingTooltipSystem+GroundWaterReservoirResult reservoir) : System.Void`  
- `private ProcessResults() : System.Void`  

## Nested types

- `Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TempResult`  
- `Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TempJob`  
- `Game.UI.Tooltip.TempWaterPumpingTooltipSystem+GroundWaterPumpJob`  
- `Game.UI.Tooltip.TempWaterPumpingTooltipSystem+GroundWaterReservoirResult`  
- `Game.UI.Tooltip.TempWaterPumpingTooltipSystem+GroundWaterReservoirJob`  
- `Game.UI.Tooltip.TempWaterPumpingTooltipSystem+TypeHandle`  

