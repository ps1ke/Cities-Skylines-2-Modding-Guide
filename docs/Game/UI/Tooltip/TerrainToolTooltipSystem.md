# Game.UI.Tooltip.TerrainToolTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TerrainToolTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.TerrainToolSystem m_TerrainTool;
    private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
    private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
    private Unity.Entities.EntityQuery m_ParameterQuery;
    private Game.UI.Tooltip.IntTooltip m_GroundwaterVolume;
    private Unity.Collections.NativeReference<Game.UI.Tooltip.TempWaterPumpingTooltipSystem+GroundWaterReservoirResult> m_ReservoirResult;

    public TerrainToolTooltipSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    private System.Void ProcessResults();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.TerrainToolSystem m_TerrainTool`  

```csharp
private Game.Tools.TerrainToolSystem m_TerrainTool;
```

- `private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem`  

```csharp
private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
```

- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  

```csharp
private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
```

- `private Unity.Entities.EntityQuery m_ParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_ParameterQuery;
```

- `private Game.UI.Tooltip.IntTooltip m_GroundwaterVolume`  

```csharp
private Game.UI.Tooltip.IntTooltip m_GroundwaterVolume;
```

- `private Unity.Collections.NativeReference<Game.UI.Tooltip.TempWaterPumpingTooltipSystem+GroundWaterReservoirResult> m_ReservoirResult`  

```csharp
private Unity.Collections.NativeReference<Game.UI.Tooltip.TempWaterPumpingTooltipSystem+GroundWaterReservoirResult> m_ReservoirResult;
```


## Constructors

- `public TerrainToolTooltipSystem()`  

```csharp
public TerrainToolTooltipSystem();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private ProcessResults() : System.Void`  

```csharp
private System.Void ProcessResults();
```


