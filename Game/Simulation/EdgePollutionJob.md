# Game.Simulation.WaterPipePollutionSystem+EdgePollutionJob

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct EdgePollutionJob : Unity.Entities.IJobChunk
{
    public Unity.Entities.ComponentTypeHandle<Game.Simulation.WaterPipeEdge> m_FlowEdgeType;
    public Unity.Entities.ComponentLookup<Game.Simulation.WaterPipeNode> m_FlowNodes;
    public Unity.Entities.Entity m_SourceNode;
    public System.Boolean m_Purify;

    public System.Void Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
    private System.Void Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
}
```


## Fields

- `public Unity.Entities.ComponentTypeHandle<Game.Simulation.WaterPipeEdge> m_FlowEdgeType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Simulation.WaterPipeEdge> m_FlowEdgeType;
```

- `public Unity.Entities.ComponentLookup<Game.Simulation.WaterPipeNode> m_FlowNodes`  

```csharp
public Unity.Entities.ComponentLookup<Game.Simulation.WaterPipeNode> m_FlowNodes;
```

- `public Unity.Entities.Entity m_SourceNode`  

```csharp
public Unity.Entities.Entity m_SourceNode;
```

- `public System.Boolean m_Purify`  

```csharp
public System.Boolean m_Purify;
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


