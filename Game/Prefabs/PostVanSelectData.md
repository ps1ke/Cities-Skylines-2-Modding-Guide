# Game.Prefabs.PostVanSelectData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct PostVanSelectData
{
    private Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_PrefabChunks;
    private Game.Prefabs.VehicleSelectRequirementData m_RequirementData;
    private Unity.Entities.EntityTypeHandle m_EntityType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.PostVanData> m_PostVanType;
    private Unity.Entities.ComponentLookup<Game.Prefabs.ObjectData> m_ObjectData;
    private Unity.Entities.ComponentLookup<Game.Prefabs.MovingObjectData> m_MovingObjectData;

    public PostVanSelectData(Unity.Entities.SystemBase system);

    public Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer commandBuffer, Unity.Mathematics.Random& random, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity vehiclePrefab, System.Boolean parked);
    public Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity vehiclePrefab, System.Boolean parked);
    private Unity.Entities.EntityArchetype GetArchetype(Unity.Entities.Entity prefab, System.Boolean parked);
    public static Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    private System.Boolean PickVehicle(Unity.Mathematics.Random& random, System.Int32 probability, System.Int32& totalProbability);
    public System.Void PostUpdate(Unity.Jobs.JobHandle jobHandle);
    public System.Void PreUpdate(Unity.Entities.SystemBase system, Game.City.CityConfigurationSystem cityConfigurationSystem, Unity.Entities.EntityQuery query, Unity.Collections.Allocator allocator, Unity.Jobs.JobHandle& jobHandle);
    public Unity.Entities.Entity SelectVehicle(Unity.Mathematics.Random& random, Unity.Mathematics.int2& mailCapacity);
}
```


## Fields

- `private Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_PrefabChunks`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_PrefabChunks;
```

- `private Game.Prefabs.VehicleSelectRequirementData m_RequirementData`  

```csharp
private Game.Prefabs.VehicleSelectRequirementData m_RequirementData;
```

- `private Unity.Entities.EntityTypeHandle m_EntityType`  

```csharp
private Unity.Entities.EntityTypeHandle m_EntityType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.PostVanData> m_PostVanType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.PostVanData> m_PostVanType;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.ObjectData> m_ObjectData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.ObjectData> m_ObjectData;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.MovingObjectData> m_MovingObjectData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.MovingObjectData> m_MovingObjectData;
```


## Constructors

- `public PostVanSelectData(Unity.Entities.SystemBase system)`  

```csharp
public PostVanSelectData(Unity.Entities.SystemBase system);
```


## Methods

- `public CreateVehicle(Unity.Entities.EntityCommandBuffer commandBuffer, Unity.Mathematics.Random& random, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity vehiclePrefab, System.Boolean parked) : Unity.Entities.Entity`  

```csharp
public Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer commandBuffer, Unity.Mathematics.Random& random, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity vehiclePrefab, System.Boolean parked);
```

- `public CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity vehiclePrefab, System.Boolean parked) : Unity.Entities.Entity`  

```csharp
public Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity vehiclePrefab, System.Boolean parked);
```

- `private GetArchetype(Unity.Entities.Entity prefab, System.Boolean parked) : Unity.Entities.EntityArchetype`  

```csharp
private Unity.Entities.EntityArchetype GetArchetype(Unity.Entities.Entity prefab, System.Boolean parked);
```

- `public static GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public static Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
```

- `private PickVehicle(Unity.Mathematics.Random& random, System.Int32 probability, System.Int32& totalProbability) : System.Boolean`  

```csharp
private System.Boolean PickVehicle(Unity.Mathematics.Random& random, System.Int32 probability, System.Int32& totalProbability);
```

- `public PostUpdate(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public System.Void PostUpdate(Unity.Jobs.JobHandle jobHandle);
```

- `public PreUpdate(Unity.Entities.SystemBase system, Game.City.CityConfigurationSystem cityConfigurationSystem, Unity.Entities.EntityQuery query, Unity.Collections.Allocator allocator, Unity.Jobs.JobHandle& jobHandle) : System.Void`  

```csharp
public System.Void PreUpdate(Unity.Entities.SystemBase system, Game.City.CityConfigurationSystem cityConfigurationSystem, Unity.Entities.EntityQuery query, Unity.Collections.Allocator allocator, Unity.Jobs.JobHandle& jobHandle);
```

- `public SelectVehicle(Unity.Mathematics.Random& random, Unity.Mathematics.int2& mailCapacity) : Unity.Entities.Entity`  

```csharp
public Unity.Entities.Entity SelectVehicle(Unity.Mathematics.Random& random, Unity.Mathematics.int2& mailCapacity);
```


