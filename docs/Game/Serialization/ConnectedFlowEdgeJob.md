# Game.Serialization.ConnectedFlowEdgeSystem+ConnectedFlowEdgeJob

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct ConnectedFlowEdgeJob : Unity.Entities.IJobChunk
{
    public Unity.Entities.EntityTypeHandle m_EntityType;
    public Unity.Entities.ComponentTypeHandle<Game.Simulation.ElectricityFlowEdge> m_ElectricityFlowEdgeType;
    public Unity.Entities.ComponentTypeHandle<Game.Simulation.WaterPipeEdge> m_WaterPipeEdgeType;
    public Unity.Entities.BufferLookup<Game.Simulation.ConnectedFlowEdge> m_ConnectedFlowEdges;

    public System.Void Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
    private System.Void Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
}
```


## Fields

- `public Unity.Entities.EntityTypeHandle m_EntityType`  

```csharp
public Unity.Entities.EntityTypeHandle m_EntityType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Simulation.ElectricityFlowEdge> m_ElectricityFlowEdgeType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Simulation.ElectricityFlowEdge> m_ElectricityFlowEdgeType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Simulation.WaterPipeEdge> m_WaterPipeEdgeType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Simulation.WaterPipeEdge> m_WaterPipeEdgeType;
```

- `public Unity.Entities.BufferLookup<Game.Simulation.ConnectedFlowEdge> m_ConnectedFlowEdges`  

```csharp
public Unity.Entities.BufferLookup<Game.Simulation.ConnectedFlowEdge> m_ConnectedFlowEdges;
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


