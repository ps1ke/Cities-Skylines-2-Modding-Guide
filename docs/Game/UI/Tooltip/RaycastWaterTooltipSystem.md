# Game.UI.Tooltip.RaycastWaterTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RaycastWaterTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.DefaultToolSystem m_DefaultTool;
    private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
    private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem;
    private Unity.Entities.EntityQuery m_InfomodeQuery;
    private Game.UI.Tooltip.IntTooltip m_WaterCapacity;
    private Game.UI.Tooltip.IntTooltip m_WaterUsage;
    private Game.UI.Tooltip.IntTooltip m_SewageCapacity;
    private Game.UI.Tooltip.IntTooltip m_SewageUsage;
    private Game.UI.Tooltip.ProgressTooltip m_WaterConsumption;
    private Game.UI.Tooltip.ProgressTooltip m_SewageConsumption;
    private Game.UI.Tooltip.IntTooltip m_WaterFlow;
    private Game.UI.Tooltip.IntTooltip m_SewageFlow;
    private Game.UI.Tooltip.RaycastWaterTooltipSystem+TypeHandle __TypeHandle;

    public RaycastWaterTooltipSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void AddEdgeFlow(Unity.Entities.Entity edge, System.Single curvePosition);
    private System.Void AddNodeFlow(Unity.Entities.Entity node, Unity.Entities.Entity edge);
    private System.Boolean IsInfomodeActivated();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.DefaultToolSystem m_DefaultTool`  

```csharp
private Game.Tools.DefaultToolSystem m_DefaultTool;
```

- `private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem`  

```csharp
private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
```

- `private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem`  

```csharp
private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem;
```

- `private Unity.Entities.EntityQuery m_InfomodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_InfomodeQuery;
```

- `private Game.UI.Tooltip.IntTooltip m_WaterCapacity`  

```csharp
private Game.UI.Tooltip.IntTooltip m_WaterCapacity;
```

- `private Game.UI.Tooltip.IntTooltip m_WaterUsage`  

```csharp
private Game.UI.Tooltip.IntTooltip m_WaterUsage;
```

- `private Game.UI.Tooltip.IntTooltip m_SewageCapacity`  

```csharp
private Game.UI.Tooltip.IntTooltip m_SewageCapacity;
```

- `private Game.UI.Tooltip.IntTooltip m_SewageUsage`  

```csharp
private Game.UI.Tooltip.IntTooltip m_SewageUsage;
```

- `private Game.UI.Tooltip.ProgressTooltip m_WaterConsumption`  

```csharp
private Game.UI.Tooltip.ProgressTooltip m_WaterConsumption;
```

- `private Game.UI.Tooltip.ProgressTooltip m_SewageConsumption`  

```csharp
private Game.UI.Tooltip.ProgressTooltip m_SewageConsumption;
```

- `private Game.UI.Tooltip.IntTooltip m_WaterFlow`  

```csharp
private Game.UI.Tooltip.IntTooltip m_WaterFlow;
```

- `private Game.UI.Tooltip.IntTooltip m_SewageFlow`  

```csharp
private Game.UI.Tooltip.IntTooltip m_SewageFlow;
```

- `private Game.UI.Tooltip.RaycastWaterTooltipSystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.Tooltip.RaycastWaterTooltipSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public RaycastWaterTooltipSystem()`  

```csharp
public RaycastWaterTooltipSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private AddEdgeFlow(Unity.Entities.Entity edge, System.Single curvePosition) : System.Void`  

```csharp
private System.Void AddEdgeFlow(Unity.Entities.Entity edge, System.Single curvePosition);
```

- `private AddNodeFlow(Unity.Entities.Entity node, Unity.Entities.Entity edge) : System.Void`  

```csharp
private System.Void AddNodeFlow(Unity.Entities.Entity node, Unity.Entities.Entity edge);
```

- `private IsInfomodeActivated() : System.Boolean`  

```csharp
private System.Boolean IsInfomodeActivated();
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

- `Game.UI.Tooltip.RaycastWaterTooltipSystem+TypeHandle`  

