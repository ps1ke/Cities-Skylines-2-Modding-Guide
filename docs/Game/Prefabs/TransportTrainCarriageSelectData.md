# Game.Prefabs.TransportTrainCarriageSelectData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct TransportTrainCarriageSelectData
{
    private Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_PrefabChunks;
    private Game.Prefabs.VehicleSelectRequirementData m_RequirementData;
    private Unity.Entities.EntityTypeHandle m_EntityType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CargoTransportVehicleData> m_CargoTransportVehicleType;

    public TransportTrainCarriageSelectData(Unity.Entities.SystemBase system);

    public static Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    private System.Boolean PickVehicle(Unity.Mathematics.Random& random, System.Int32 probability, System.Int32& totalProbability);
    public System.Void PostUpdate(Unity.Jobs.JobHandle jobHandle);
    public System.Void PreUpdate(Unity.Entities.SystemBase system, Game.City.CityConfigurationSystem cityConfigurationSystem, Unity.Entities.EntityQuery query, Unity.Collections.Allocator allocator, Unity.Jobs.JobHandle& jobHandle);
    public Unity.Entities.Entity SelectCarriagePrefab(Unity.Mathematics.Random& random, Game.Economy.Resource resource, System.Int32 amount);
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

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CargoTransportVehicleData> m_CargoTransportVehicleType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CargoTransportVehicleData> m_CargoTransportVehicleType;
```


## Constructors

- `public TransportTrainCarriageSelectData(Unity.Entities.SystemBase system)`  

```csharp
public TransportTrainCarriageSelectData(Unity.Entities.SystemBase system);
```


## Methods

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

- `public SelectCarriagePrefab(Unity.Mathematics.Random& random, Game.Economy.Resource resource, System.Int32 amount) : Unity.Entities.Entity`  

```csharp
public Unity.Entities.Entity SelectCarriagePrefab(Unity.Mathematics.Random& random, Game.Economy.Resource resource, System.Int32 amount);
```


