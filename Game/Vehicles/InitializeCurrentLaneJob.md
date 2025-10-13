# Game.Vehicles.ReferencesSystem+InitializeCurrentLaneJob

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct InitializeCurrentLaneJob : Unity.Entities.IJobChunk
{
    public Unity.Entities.ComponentTypeHandle<Game.Objects.Transform> m_TransformType;
    public Unity.Entities.ComponentTypeHandle<Game.Vehicles.CarCurrentLane> m_CarCurrentLaneType;
    public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData;
    public Unity.Entities.ComponentLookup<Game.Net.CarLane> m_CarLaneData;
    public Unity.Entities.ComponentLookup<Game.Net.MasterLane> m_MasterLaneData;
    public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData;
    public Unity.Entities.BufferLookup<Game.Net.SubLane> m_LaneData;

    public System.Void Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
    private System.Void Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
}
```


## Fields

- `public Unity.Entities.ComponentTypeHandle<Game.Objects.Transform> m_TransformType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Objects.Transform> m_TransformType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Vehicles.CarCurrentLane> m_CarCurrentLaneType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Vehicles.CarCurrentLane> m_CarCurrentLaneType;
```

- `public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.CarLane> m_CarLaneData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.CarLane> m_CarLaneData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.MasterLane> m_MasterLaneData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.MasterLane> m_MasterLaneData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData;
```

- `public Unity.Entities.BufferLookup<Game.Net.SubLane> m_LaneData`  

```csharp
public Unity.Entities.BufferLookup<Game.Net.SubLane> m_LaneData;
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


