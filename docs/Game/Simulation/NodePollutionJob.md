# Game.Simulation.WaterPipePollutionSystem+NodePollutionJob

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct NodePollutionJob : Unity.Entities.IJobChunk
{
    public Unity.Entities.EntityTypeHandle m_EntityType;
    public Unity.Entities.BufferTypeHandle<Game.Simulation.ConnectedFlowEdge> m_FlowConnectionType;
    public Unity.Entities.ComponentTypeHandle<Game.Simulation.WaterPipeNode> m_NodeType;
    public Unity.Entities.ComponentLookup<Game.Simulation.WaterPipeEdge> m_FlowEdges;
    public System.Single m_StaleWaterPipePurification;

    public System.Void Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
    private System.Void Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
}
```


## Fields

- `public Unity.Entities.EntityTypeHandle m_EntityType`  

```csharp
public Unity.Entities.EntityTypeHandle m_EntityType;
```

- `public Unity.Entities.BufferTypeHandle<Game.Simulation.ConnectedFlowEdge> m_FlowConnectionType`  

```csharp
public Unity.Entities.BufferTypeHandle<Game.Simulation.ConnectedFlowEdge> m_FlowConnectionType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Simulation.WaterPipeNode> m_NodeType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Simulation.WaterPipeNode> m_NodeType;
```

- `public Unity.Entities.ComponentLookup<Game.Simulation.WaterPipeEdge> m_FlowEdges`  

```csharp
public Unity.Entities.ComponentLookup<Game.Simulation.WaterPipeEdge> m_FlowEdges;
```

- `public System.Single m_StaleWaterPipePurification`  

```csharp
public System.Single m_StaleWaterPipePurification;
```


## Methods

- `public Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  

```csharp
public System.Void Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
```

- `private Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  

```csharp
private System.Void Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
```


