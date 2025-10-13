# Game.Prefabs.PersonalCarSelectData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct PersonalCarSelectData
{
    private Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_PrefabChunks;
    private Game.Prefabs.VehicleSelectRequirementData m_RequirementData;
    private Unity.Entities.EntityTypeHandle m_EntityType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarData> m_CarDataType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.PersonalCarData> m_PersonalCarDataType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTrailerData> m_CarTrailerDataType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTractorData> m_CarTractorDataType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.ObjectData> m_ObjectDataType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.MovingObjectData> m_MovingObjectDataType;

    public PersonalCarSelectData(Unity.Entities.SystemBase system);

    private System.Void CalculateProbability(System.Int32 passengerAmount, System.Int32 baggageAmount, Game.Prefabs.PersonalCarSelectData+CarData firstData, Game.Prefabs.PersonalCarSelectData+CarData secondData, System.Int32& probability, System.Int32& offset);
    private System.Void CheckTractors(System.Int32 passengerAmount, System.Int32 baggageAmount, System.Int32 extraOffset, Game.Prefabs.PersonalCarSelectData+CarData secondData, System.Boolean noSlowVehicles, Unity.Mathematics.Random& random, Game.Prefabs.PersonalCarSelectData+CarData& bestFirst, Game.Prefabs.PersonalCarSelectData+CarData& bestSecond, System.Int32& totalProbability, System.Int32& bestOffset);
    private System.Void CheckTrailers(System.Int32 passengerAmount, System.Int32 baggageAmount, System.Int32 extraOffset, Game.Prefabs.PersonalCarSelectData+CarData firstData, System.Boolean emptyOnly, System.Boolean noSlowVehicles, Unity.Mathematics.Random& random, Game.Prefabs.PersonalCarSelectData+CarData& bestFirst, Game.Prefabs.PersonalCarSelectData+CarData& bestSecond, System.Int32& totalProbability, System.Int32& bestOffset);
    public Unity.Entities.Entity CreateTrailer(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, System.Int32 passengerAmount, System.Int32 baggageAmount, System.Boolean noSlowVehicles, Unity.Entities.Entity tractorPrefab, Game.Objects.Transform tractorTransform, Game.Vehicles.PersonalCarFlags state, System.Boolean stopped, System.UInt32 delay);
    public Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, System.Int32 passengerAmount, System.Int32 baggageAmount, System.Boolean avoidTrailers, System.Boolean noSlowVehicles, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity keeper, Game.Vehicles.PersonalCarFlags state, System.Boolean stopped, System.UInt32 delay);
    public Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, System.Int32 passengerAmount, System.Int32 baggageAmount, System.Boolean avoidTrailers, System.Boolean noSlowVehicles, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity keeper, Game.Vehicles.PersonalCarFlags state, System.Boolean stopped, System.UInt32 delay, Unity.Entities.Entity& trailer, Unity.Entities.Entity& vehiclePrefab, Unity.Entities.Entity& trailerPrefab);
    public Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer commandBuffer, Unity.Mathematics.Random& random, System.Int32 passengerAmount, System.Int32 baggageAmount, System.Boolean avoidTrailers, System.Boolean noSlowVehicles, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity keeper, Game.Vehicles.PersonalCarFlags state, System.Boolean stopped, System.UInt32 delay);
    private Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Prefabs.PersonalCarSelectData+CarData data, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity keeper, Game.Vehicles.PersonalCarFlags state, System.Boolean stopped, System.UInt32 delay);
    private Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer commandBuffer, Unity.Mathematics.Random& random, Game.Prefabs.PersonalCarSelectData+CarData data, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity keeper, Game.Vehicles.PersonalCarFlags state, System.Boolean stopped, System.UInt32 delay);
    public static Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    private System.Boolean GetVehicleData(Unity.Mathematics.Random& random, System.Int32 passengerAmount, System.Int32 baggageAmount, System.Boolean avoidTrailers, System.Boolean noSlowVehicles, Game.Prefabs.PersonalCarSelectData+CarData& bestFirst, Game.Prefabs.PersonalCarSelectData+CarData& bestSecond);
    private System.Boolean PickVehicle(Unity.Mathematics.Random& random, System.Int32 probability, System.Int32 offset, System.Int32& totalProbability, System.Int32& bestOffset);
    public System.Void PostUpdate(Unity.Jobs.JobHandle jobHandle);
    public System.Void PreUpdate(Unity.Entities.SystemBase system, Game.City.CityConfigurationSystem cityConfigurationSystem, Unity.Entities.EntityQuery query, Unity.Collections.Allocator allocator, Unity.Jobs.JobHandle& jobHandle);
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

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarData> m_CarDataType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarData> m_CarDataType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.PersonalCarData> m_PersonalCarDataType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.PersonalCarData> m_PersonalCarDataType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTrailerData> m_CarTrailerDataType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTrailerData> m_CarTrailerDataType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTractorData> m_CarTractorDataType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTractorData> m_CarTractorDataType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.ObjectData> m_ObjectDataType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.ObjectData> m_ObjectDataType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.MovingObjectData> m_MovingObjectDataType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.MovingObjectData> m_MovingObjectDataType;
```


## Constructors

- `public PersonalCarSelectData(Unity.Entities.SystemBase system)`  

```csharp
public PersonalCarSelectData(Unity.Entities.SystemBase system);
```


## Methods

- `private CalculateProbability(System.Int32 passengerAmount, System.Int32 baggageAmount, Game.Prefabs.PersonalCarSelectData+CarData firstData, Game.Prefabs.PersonalCarSelectData+CarData secondData, System.Int32& probability, System.Int32& offset) : System.Void`  

```csharp
private System.Void CalculateProbability(System.Int32 passengerAmount, System.Int32 baggageAmount, Game.Prefabs.PersonalCarSelectData+CarData firstData, Game.Prefabs.PersonalCarSelectData+CarData secondData, System.Int32& probability, System.Int32& offset);
```

- `private CheckTractors(System.Int32 passengerAmount, System.Int32 baggageAmount, System.Int32 extraOffset, Game.Prefabs.PersonalCarSelectData+CarData secondData, System.Boolean noSlowVehicles, Unity.Mathematics.Random& random, Game.Prefabs.PersonalCarSelectData+CarData& bestFirst, Game.Prefabs.PersonalCarSelectData+CarData& bestSecond, System.Int32& totalProbability, System.Int32& bestOffset) : System.Void`  

```csharp
private System.Void CheckTractors(System.Int32 passengerAmount, System.Int32 baggageAmount, System.Int32 extraOffset, Game.Prefabs.PersonalCarSelectData+CarData secondData, System.Boolean noSlowVehicles, Unity.Mathematics.Random& random, Game.Prefabs.PersonalCarSelectData+CarData& bestFirst, Game.Prefabs.PersonalCarSelectData+CarData& bestSecond, System.Int32& totalProbability, System.Int32& bestOffset);
```

- `private CheckTrailers(System.Int32 passengerAmount, System.Int32 baggageAmount, System.Int32 extraOffset, Game.Prefabs.PersonalCarSelectData+CarData firstData, System.Boolean emptyOnly, System.Boolean noSlowVehicles, Unity.Mathematics.Random& random, Game.Prefabs.PersonalCarSelectData+CarData& bestFirst, Game.Prefabs.PersonalCarSelectData+CarData& bestSecond, System.Int32& totalProbability, System.Int32& bestOffset) : System.Void`  

```csharp
private System.Void CheckTrailers(System.Int32 passengerAmount, System.Int32 baggageAmount, System.Int32 extraOffset, Game.Prefabs.PersonalCarSelectData+CarData firstData, System.Boolean emptyOnly, System.Boolean noSlowVehicles, Unity.Mathematics.Random& random, Game.Prefabs.PersonalCarSelectData+CarData& bestFirst, Game.Prefabs.PersonalCarSelectData+CarData& bestSecond, System.Int32& totalProbability, System.Int32& bestOffset);
```

- `public CreateTrailer(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, System.Int32 passengerAmount, System.Int32 baggageAmount, System.Boolean noSlowVehicles, Unity.Entities.Entity tractorPrefab, Game.Objects.Transform tractorTransform, Game.Vehicles.PersonalCarFlags state, System.Boolean stopped, System.UInt32 delay = 0) : Unity.Entities.Entity`  

```csharp
public Unity.Entities.Entity CreateTrailer(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, System.Int32 passengerAmount, System.Int32 baggageAmount, System.Boolean noSlowVehicles, Unity.Entities.Entity tractorPrefab, Game.Objects.Transform tractorTransform, Game.Vehicles.PersonalCarFlags state, System.Boolean stopped, System.UInt32 delay);
```

- `public CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, System.Int32 passengerAmount, System.Int32 baggageAmount, System.Boolean avoidTrailers, System.Boolean noSlowVehicles, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity keeper, Game.Vehicles.PersonalCarFlags state, System.Boolean stopped, System.UInt32 delay = 0) : Unity.Entities.Entity`  

```csharp
public Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, System.Int32 passengerAmount, System.Int32 baggageAmount, System.Boolean avoidTrailers, System.Boolean noSlowVehicles, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity keeper, Game.Vehicles.PersonalCarFlags state, System.Boolean stopped, System.UInt32 delay);
```

- `public CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, System.Int32 passengerAmount, System.Int32 baggageAmount, System.Boolean avoidTrailers, System.Boolean noSlowVehicles, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity keeper, Game.Vehicles.PersonalCarFlags state, System.Boolean stopped, System.UInt32 delay, Unity.Entities.Entity& trailer, Unity.Entities.Entity& vehiclePrefab, Unity.Entities.Entity& trailerPrefab) : Unity.Entities.Entity`  

```csharp
public Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, System.Int32 passengerAmount, System.Int32 baggageAmount, System.Boolean avoidTrailers, System.Boolean noSlowVehicles, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity keeper, Game.Vehicles.PersonalCarFlags state, System.Boolean stopped, System.UInt32 delay, Unity.Entities.Entity& trailer, Unity.Entities.Entity& vehiclePrefab, Unity.Entities.Entity& trailerPrefab);
```

- `public CreateVehicle(Unity.Entities.EntityCommandBuffer commandBuffer, Unity.Mathematics.Random& random, System.Int32 passengerAmount, System.Int32 baggageAmount, System.Boolean avoidTrailers, System.Boolean noSlowVehicles, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity keeper, Game.Vehicles.PersonalCarFlags state, System.Boolean stopped, System.UInt32 delay = 0) : Unity.Entities.Entity`  

```csharp
public Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer commandBuffer, Unity.Mathematics.Random& random, System.Int32 passengerAmount, System.Int32 baggageAmount, System.Boolean avoidTrailers, System.Boolean noSlowVehicles, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity keeper, Game.Vehicles.PersonalCarFlags state, System.Boolean stopped, System.UInt32 delay);
```

- `private CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Prefabs.PersonalCarSelectData+CarData data, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity keeper, Game.Vehicles.PersonalCarFlags state, System.Boolean stopped, System.UInt32 delay) : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Prefabs.PersonalCarSelectData+CarData data, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity keeper, Game.Vehicles.PersonalCarFlags state, System.Boolean stopped, System.UInt32 delay);
```

- `private CreateVehicle(Unity.Entities.EntityCommandBuffer commandBuffer, Unity.Mathematics.Random& random, Game.Prefabs.PersonalCarSelectData+CarData data, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity keeper, Game.Vehicles.PersonalCarFlags state, System.Boolean stopped, System.UInt32 delay) : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer commandBuffer, Unity.Mathematics.Random& random, Game.Prefabs.PersonalCarSelectData+CarData data, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity keeper, Game.Vehicles.PersonalCarFlags state, System.Boolean stopped, System.UInt32 delay);
```

- `public static GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public static Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
```

- `private GetVehicleData(Unity.Mathematics.Random& random, System.Int32 passengerAmount, System.Int32 baggageAmount, System.Boolean avoidTrailers, System.Boolean noSlowVehicles, Game.Prefabs.PersonalCarSelectData+CarData& bestFirst, Game.Prefabs.PersonalCarSelectData+CarData& bestSecond) : System.Boolean`  

```csharp
private System.Boolean GetVehicleData(Unity.Mathematics.Random& random, System.Int32 passengerAmount, System.Int32 baggageAmount, System.Boolean avoidTrailers, System.Boolean noSlowVehicles, Game.Prefabs.PersonalCarSelectData+CarData& bestFirst, Game.Prefabs.PersonalCarSelectData+CarData& bestSecond);
```

- `private PickVehicle(Unity.Mathematics.Random& random, System.Int32 probability, System.Int32 offset, System.Int32& totalProbability, System.Int32& bestOffset) : System.Boolean`  

```csharp
private System.Boolean PickVehicle(Unity.Mathematics.Random& random, System.Int32 probability, System.Int32 offset, System.Int32& totalProbability, System.Int32& bestOffset);
```

- `public PostUpdate(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public System.Void PostUpdate(Unity.Jobs.JobHandle jobHandle);
```

- `public PreUpdate(Unity.Entities.SystemBase system, Game.City.CityConfigurationSystem cityConfigurationSystem, Unity.Entities.EntityQuery query, Unity.Collections.Allocator allocator, Unity.Jobs.JobHandle& jobHandle) : System.Void`  

```csharp
public System.Void PreUpdate(Unity.Entities.SystemBase system, Game.City.CityConfigurationSystem cityConfigurationSystem, Unity.Entities.EntityQuery query, Unity.Collections.Allocator allocator, Unity.Jobs.JobHandle& jobHandle);
```


## Nested types

- `Game.Prefabs.PersonalCarSelectData+CarData`  

