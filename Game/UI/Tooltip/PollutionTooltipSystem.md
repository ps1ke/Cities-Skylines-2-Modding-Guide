# Game.UI.Tooltip.PollutionTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PollutionTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.DefaultToolSystem m_DefaultTool;
    private Game.Common.RaycastSystem m_RaycastSystem;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
    private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
    private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
    private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Unity.Entities.EntityQuery m_ActiveInfomodeQuery;
    private Game.UI.Tooltip.IntTooltip m_Garbage;
    private Game.UI.Tooltip.IntTooltip m_AirPollution;
    private Game.UI.Tooltip.IntTooltip m_GroundPollution;
    private Game.UI.Tooltip.IntTooltip m_NoisePollution;
    private Game.UI.Tooltip.IntTooltip m_WaterPollution;
    private Game.Common.RaycastResult m_RaycastResult;

    private Game.Common.RaycastResult raycastResult { private get; private set; }

    public PollutionTooltipSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.DefaultToolSystem m_DefaultTool`  

```csharp
private Game.Tools.DefaultToolSystem m_DefaultTool;
```

- `private Game.Common.RaycastSystem m_RaycastSystem`  

```csharp
private Game.Common.RaycastSystem m_RaycastSystem;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  

```csharp
private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
```

- `private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem`  

```csharp
private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
```

- `private Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  

```csharp
private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
```

- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  

```csharp
private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Unity.Entities.EntityQuery m_ActiveInfomodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_ActiveInfomodeQuery;
```

- `private Game.UI.Tooltip.IntTooltip m_Garbage`  

```csharp
private Game.UI.Tooltip.IntTooltip m_Garbage;
```

- `private Game.UI.Tooltip.IntTooltip m_AirPollution`  

```csharp
private Game.UI.Tooltip.IntTooltip m_AirPollution;
```

- `private Game.UI.Tooltip.IntTooltip m_GroundPollution`  

```csharp
private Game.UI.Tooltip.IntTooltip m_GroundPollution;
```

- `private Game.UI.Tooltip.IntTooltip m_NoisePollution`  

```csharp
private Game.UI.Tooltip.IntTooltip m_NoisePollution;
```

- `private Game.UI.Tooltip.IntTooltip m_WaterPollution`  

```csharp
private Game.UI.Tooltip.IntTooltip m_WaterPollution;
```

- `private Game.Common.RaycastResult m_RaycastResult`  

```csharp
private Game.Common.RaycastResult m_RaycastResult;
```


## Properties

- `private Game.Common.RaycastResult raycastResult { private get; private set }`  

```csharp
private Game.Common.RaycastResult raycastResult { private get; private set; }
```


## Constructors

- `public PollutionTooltipSystem()`  

```csharp
public PollutionTooltipSystem();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


