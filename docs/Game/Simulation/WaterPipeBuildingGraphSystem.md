# Game.Simulation.WaterPipeBuildingGraphSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterPipeBuildingGraphSystem : Game.GameSystemBase
{
    private Game.Simulation.WaterPipeRoadConnectionGraphSystem m_WaterPipeRoadConnectionGraphSystem;
    private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem;
    private Game.Common.ModificationBarrier4B m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_UpdatedBuildingQuery;
    private Game.Simulation.WaterPipeBuildingGraphSystem+TypeHandle __TypeHandle;

    public WaterPipeBuildingGraphSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    internal static Unity.Entities.EntityQueryDesc <OnCreate>g__CreatedUpdatedBuildingDesc|4_0(Unity.Entities.ComponentType[] all);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.WaterPipeRoadConnectionGraphSystem m_WaterPipeRoadConnectionGraphSystem`  

```csharp
private Game.Simulation.WaterPipeRoadConnectionGraphSystem m_WaterPipeRoadConnectionGraphSystem;
```

- `private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem`  

```csharp
private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem;
```

- `private Game.Common.ModificationBarrier4B m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4B m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_UpdatedBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedBuildingQuery;
```

- `private Game.Simulation.WaterPipeBuildingGraphSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WaterPipeBuildingGraphSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public WaterPipeBuildingGraphSystem()`  

```csharp
public WaterPipeBuildingGraphSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `internal static <OnCreate>g__CreatedUpdatedBuildingDesc|4_0(Unity.Entities.ComponentType[] all) : Unity.Entities.EntityQueryDesc`  

```csharp
internal static Unity.Entities.EntityQueryDesc <OnCreate>g__CreatedUpdatedBuildingDesc|4_0(Unity.Entities.ComponentType[] all);
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

- `Game.Simulation.WaterPipeBuildingGraphSystem+UpdateBuildingConnectionsJob`  
- `Game.Simulation.WaterPipeBuildingGraphSystem+TypeHandle`  

