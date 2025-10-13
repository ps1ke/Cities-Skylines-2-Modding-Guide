# Game.Areas.RaycastJobs+RaycastLabelsJob

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct RaycastLabelsJob : Unity.Entities.IJobChunk
{
    public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input;
    public Unity.Mathematics.float3 m_CameraRight;
    public Unity.Entities.EntityTypeHandle m_EntityType;
    public Unity.Entities.ComponentTypeHandle<Game.Areas.Geometry> m_GeometryType;
    public Unity.Entities.BufferTypeHandle<Game.Areas.LabelExtents> m_LabelExtentsType;
    public Colossal.Collections.NativeAccumulator<Game.Common.RaycastResult> m_Results;

    public System.Void Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
    private System.Void Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
}
```


## Fields

- `public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input`  

```csharp
public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input;
```

- `public Unity.Mathematics.float3 m_CameraRight`  

```csharp
public Unity.Mathematics.float3 m_CameraRight;
```

- `public Unity.Entities.EntityTypeHandle m_EntityType`  

```csharp
public Unity.Entities.EntityTypeHandle m_EntityType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Areas.Geometry> m_GeometryType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Areas.Geometry> m_GeometryType;
```

- `public Unity.Entities.BufferTypeHandle<Game.Areas.LabelExtents> m_LabelExtentsType`  

```csharp
public Unity.Entities.BufferTypeHandle<Game.Areas.LabelExtents> m_LabelExtentsType;
```

- `public Colossal.Collections.NativeAccumulator<Game.Common.RaycastResult> m_Results`  

```csharp
public Colossal.Collections.NativeAccumulator<Game.Common.RaycastResult> m_Results;
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


