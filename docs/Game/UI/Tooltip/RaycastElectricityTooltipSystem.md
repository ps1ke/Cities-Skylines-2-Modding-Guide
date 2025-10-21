# Game.UI.Tooltip.RaycastElectricityTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RaycastElectricityTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.DefaultToolSystem m_DefaultTool;
    private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
    private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem;
    private Unity.Entities.EntityQuery m_InfomodeQuery;
    private Game.UI.Tooltip.IntTooltip m_Production;
    private Game.UI.Tooltip.IntTooltip m_TransformerCapacity;
    private Game.UI.Tooltip.IntTooltip m_Usage;
    private Game.UI.Tooltip.IntTooltip m_BatteryFlow;
    private Game.UI.Tooltip.IntTooltip m_BatteryCharge;
    private Game.UI.Tooltip.ProgressTooltip m_Consumption;
    private Game.UI.Tooltip.ProgressTooltip m_Flow;
    private Game.UI.Tooltip.RaycastElectricityTooltipSystem+TypeHandle __TypeHandle;

    public RaycastElectricityTooltipSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void AddEdgeFlow(Unity.Entities.Entity edge, System.Single curvePosition);
    private System.Void AddNodeFlow(Unity.Entities.Entity node, Unity.Entities.Entity edge);
    private System.Boolean HasBottleneck(Unity.Entities.Entity building);
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

- `private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem`  

```csharp
private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem;
```

- `private Unity.Entities.EntityQuery m_InfomodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_InfomodeQuery;
```

- `private Game.UI.Tooltip.IntTooltip m_Production`  

```csharp
private Game.UI.Tooltip.IntTooltip m_Production;
```

- `private Game.UI.Tooltip.IntTooltip m_TransformerCapacity`  

```csharp
private Game.UI.Tooltip.IntTooltip m_TransformerCapacity;
```

- `private Game.UI.Tooltip.IntTooltip m_Usage`  

```csharp
private Game.UI.Tooltip.IntTooltip m_Usage;
```

- `private Game.UI.Tooltip.IntTooltip m_BatteryFlow`  

```csharp
private Game.UI.Tooltip.IntTooltip m_BatteryFlow;
```

- `private Game.UI.Tooltip.IntTooltip m_BatteryCharge`  

```csharp
private Game.UI.Tooltip.IntTooltip m_BatteryCharge;
```

- `private Game.UI.Tooltip.ProgressTooltip m_Consumption`  

```csharp
private Game.UI.Tooltip.ProgressTooltip m_Consumption;
```

- `private Game.UI.Tooltip.ProgressTooltip m_Flow`  

```csharp
private Game.UI.Tooltip.ProgressTooltip m_Flow;
```

- `private Game.UI.Tooltip.RaycastElectricityTooltipSystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.Tooltip.RaycastElectricityTooltipSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public RaycastElectricityTooltipSystem()`  

```csharp
public RaycastElectricityTooltipSystem();
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

- `private HasBottleneck(Unity.Entities.Entity building) : System.Boolean`  

```csharp
private System.Boolean HasBottleneck(Unity.Entities.Entity building);
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

- `Game.UI.Tooltip.RaycastElectricityTooltipSystem+TypeHandle`  

