# Game.Rendering.NetColorSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NetColorSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_ZonePreferenceParameterGroup;
    private Unity.Entities.EntityQuery m_EdgeQuery;
    private Unity.Entities.EntityQuery m_NodeQuery;
    private Unity.Entities.EntityQuery m_LaneQuery;
    private Unity.Entities.EntityQuery m_InfomodeQuery;
    private Unity.Entities.EntityQuery m_ProcessQuery;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.ZoneToolSystem m_ZoneToolSystem;
    private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
    private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
    private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem;
    private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem;
    private Game.Rendering.NetColorSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1733354667_0;

    public NetColorSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ZonePreferenceParameterGroup`  

```csharp
private Unity.Entities.EntityQuery m_ZonePreferenceParameterGroup;
```

- `private Unity.Entities.EntityQuery m_EdgeQuery`  

```csharp
private Unity.Entities.EntityQuery m_EdgeQuery;
```

- `private Unity.Entities.EntityQuery m_NodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_NodeQuery;
```

- `private Unity.Entities.EntityQuery m_LaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_LaneQuery;
```

- `private Unity.Entities.EntityQuery m_InfomodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_InfomodeQuery;
```

- `private Unity.Entities.EntityQuery m_ProcessQuery`  

```csharp
private Unity.Entities.EntityQuery m_ProcessQuery;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.ZoneToolSystem m_ZoneToolSystem`  

```csharp
private Game.Tools.ZoneToolSystem m_ZoneToolSystem;
```

- `private Game.Tools.ObjectToolSystem m_ObjectToolSystem`  

```csharp
private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
```

- `private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem`  

```csharp
private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  

```csharp
private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
```

- `private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem`  

```csharp
private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem;
```

- `private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem`  

```csharp
private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem;
```

- `private Game.Rendering.NetColorSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.NetColorSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1733354667_0`  

```csharp
private Unity.Entities.EntityQuery __query_1733354667_0;
```


## Constructors

- `public NetColorSystem()`  

```csharp
public NetColorSystem();
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

- `Game.Rendering.NetColorSystem+UpdateEdgeColorsJob`  
- `Game.Rendering.NetColorSystem+UpdateNodeColorsJob`  
- `Game.Rendering.NetColorSystem+UpdateEdgeColors2Job`  
- `Game.Rendering.NetColorSystem+LaneColorJob`  
- `Game.Rendering.NetColorSystem+TypeHandle`  

