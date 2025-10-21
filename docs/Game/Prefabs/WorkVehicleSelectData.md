# Game.Prefabs.WorkVehicleSelectData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct WorkVehicleSelectData
{
    private Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_PrefabChunks;
    private Game.Prefabs.VehicleSelectRequirementData m_RequirementData;
    private Unity.Entities.EntityTypeHandle m_EntityType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.WorkVehicleData> m_WorkVehicleDataType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTrailerData> m_CarTrailerDataType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTractorData> m_CarTractorDataType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarData> m_CarDataType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.WatercraftData> m_WatercraftDataType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.ObjectData> m_ObjectDataType;

    public WorkVehicleSelectData(Unity.Entities.SystemBase system);

    private System.Void CheckTractors(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, Game.Prefabs.WorkVehicleSelectData+VehicleData secondData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability);
    private System.Void CheckTractors(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, Game.Prefabs.WorkVehicleSelectData+VehicleData secondData, Game.Prefabs.WorkVehicleSelectData+VehicleData thirdData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability);
    private System.Void CheckTractors(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, Game.Prefabs.WorkVehicleSelectData+VehicleData secondData, Game.Prefabs.WorkVehicleSelectData+VehicleData thirdData, Game.Prefabs.WorkVehicleSelectData+VehicleData forthData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability);
    private System.Void CheckTrailers(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, System.Boolean firstIsTrailer, Game.Prefabs.WorkVehicleSelectData+VehicleData firstData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability);
    private System.Void CheckTrailers(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, System.Boolean firstIsTrailer, Game.Prefabs.WorkVehicleSelectData+VehicleData firstData, Game.Prefabs.WorkVehicleSelectData+VehicleData secondData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability);
    private System.Void CheckTrailers(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, Game.Prefabs.WorkVehicleSelectData+VehicleData firstData, Game.Prefabs.WorkVehicleSelectData+VehicleData secondData, Game.Prefabs.WorkVehicleSelectData+VehicleData thirdData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability);
    public Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Net.RoadTypes roadTypes, Game.Vehicles.SizeClass sizeClass, Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, System.Single& workAmount, Game.Objects.Transform transform, Unity.Entities.Entity source, Game.Vehicles.WorkVehicleFlags state);
    private Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData data, Game.Vehicles.VehicleWorkType workType, System.Single& workAmount, Game.Objects.Transform transform, Unity.Entities.Entity source, Game.Vehicles.WorkVehicleFlags state);
    public static Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    private System.Boolean PickVehicle(Unity.Mathematics.Random& random, System.Int32 probability, System.Int32& totalProbability);
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

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.WorkVehicleData> m_WorkVehicleDataType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.WorkVehicleData> m_WorkVehicleDataType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTrailerData> m_CarTrailerDataType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTrailerData> m_CarTrailerDataType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTractorData> m_CarTractorDataType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTractorData> m_CarTractorDataType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarData> m_CarDataType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarData> m_CarDataType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.WatercraftData> m_WatercraftDataType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.WatercraftData> m_WatercraftDataType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.ObjectData> m_ObjectDataType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.ObjectData> m_ObjectDataType;
```


## Constructors

- `public WorkVehicleSelectData(Unity.Entities.SystemBase system)`  

```csharp
public WorkVehicleSelectData(Unity.Entities.SystemBase system);
```


## Methods

- `private CheckTractors(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, Game.Prefabs.WorkVehicleSelectData+VehicleData secondData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability) : System.Void`  

```csharp
private System.Void CheckTractors(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, Game.Prefabs.WorkVehicleSelectData+VehicleData secondData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability);
```

- `private CheckTractors(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, Game.Prefabs.WorkVehicleSelectData+VehicleData secondData, Game.Prefabs.WorkVehicleSelectData+VehicleData thirdData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability) : System.Void`  

```csharp
private System.Void CheckTractors(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, Game.Prefabs.WorkVehicleSelectData+VehicleData secondData, Game.Prefabs.WorkVehicleSelectData+VehicleData thirdData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability);
```

- `private CheckTractors(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, Game.Prefabs.WorkVehicleSelectData+VehicleData secondData, Game.Prefabs.WorkVehicleSelectData+VehicleData thirdData, Game.Prefabs.WorkVehicleSelectData+VehicleData forthData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability) : System.Void`  

```csharp
private System.Void CheckTractors(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, Game.Prefabs.WorkVehicleSelectData+VehicleData secondData, Game.Prefabs.WorkVehicleSelectData+VehicleData thirdData, Game.Prefabs.WorkVehicleSelectData+VehicleData forthData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability);
```

- `private CheckTrailers(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, System.Boolean firstIsTrailer, Game.Prefabs.WorkVehicleSelectData+VehicleData firstData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability) : System.Void`  

```csharp
private System.Void CheckTrailers(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, System.Boolean firstIsTrailer, Game.Prefabs.WorkVehicleSelectData+VehicleData firstData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability);
```

- `private CheckTrailers(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, System.Boolean firstIsTrailer, Game.Prefabs.WorkVehicleSelectData+VehicleData firstData, Game.Prefabs.WorkVehicleSelectData+VehicleData secondData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability) : System.Void`  

```csharp
private System.Void CheckTrailers(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, System.Boolean firstIsTrailer, Game.Prefabs.WorkVehicleSelectData+VehicleData firstData, Game.Prefabs.WorkVehicleSelectData+VehicleData secondData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability);
```

- `private CheckTrailers(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, Game.Prefabs.WorkVehicleSelectData+VehicleData firstData, Game.Prefabs.WorkVehicleSelectData+VehicleData secondData, Game.Prefabs.WorkVehicleSelectData+VehicleData thirdData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability) : System.Void`  

```csharp
private System.Void CheckTrailers(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, Game.Prefabs.WorkVehicleSelectData+VehicleData firstData, Game.Prefabs.WorkVehicleSelectData+VehicleData secondData, Game.Prefabs.WorkVehicleSelectData+VehicleData thirdData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability);
```

- `public CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Net.RoadTypes roadTypes, Game.Vehicles.SizeClass sizeClass, Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, System.Single& workAmount, Game.Objects.Transform transform, Unity.Entities.Entity source, Game.Vehicles.WorkVehicleFlags state) : Unity.Entities.Entity`  

```csharp
public Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Net.RoadTypes roadTypes, Game.Vehicles.SizeClass sizeClass, Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, System.Single& workAmount, Game.Objects.Transform transform, Unity.Entities.Entity source, Game.Vehicles.WorkVehicleFlags state);
```

- `private CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData data, Game.Vehicles.VehicleWorkType workType, System.Single& workAmount, Game.Objects.Transform transform, Unity.Entities.Entity source, Game.Vehicles.WorkVehicleFlags state) : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData data, Game.Vehicles.VehicleWorkType workType, System.Single& workAmount, Game.Objects.Transform transform, Unity.Entities.Entity source, Game.Vehicles.WorkVehicleFlags state);
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


## Nested types

- `Game.Prefabs.WorkVehicleSelectData+VehicleData`  

