# Game.Prefabs.TransportVehicleSelectData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct TransportVehicleSelectData
{
    private Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_PrefabChunks;
    private Game.Prefabs.VehicleSelectRequirementData m_RequirementData;
    private Unity.Entities.EntityTypeHandle m_EntityType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.PublicTransportVehicleData> m_PublicTransportVehicleType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CargoTransportVehicleData> m_CargoTransportVehicleType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.TrainData> m_TrainType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.TrainEngineData> m_TrainEngineType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.TrainCarriageData> m_TrainCarriageType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.MultipleUnitTrainData> m_MultipleUnitTrainType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.TaxiData> m_TaxiType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarData> m_CarType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.AircraftData> m_AircraftType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.AirplaneData> m_AirplaneType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.HelicopterData> m_HelicopterType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.WatercraftData> m_WatercraftType;
    private Unity.Entities.ComponentLookup<Game.Prefabs.ObjectData> m_ObjectData;
    private Unity.Entities.ComponentLookup<Game.Prefabs.MovingObjectData> m_MovingObjectData;
    private Unity.Entities.ComponentLookup<Game.Prefabs.TrainObjectData> m_TrainObjectData;
    private Unity.Entities.ComponentLookup<Game.Prefabs.PublicTransportVehicleData> m_PublicTransportVehicleData;
    private Unity.Entities.ComponentLookup<Game.Prefabs.CargoTransportVehicleData> m_CargoTransportVehicleData;
    private Unity.Entities.BufferLookup<Game.Prefabs.VehicleCarriageElement> m_VehicleCarriages;

    public TransportVehicleSelectData(Unity.Entities.SystemBase system);

    private System.Void AddTransportComponents(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Game.Prefabs.PublicTransportPurpose publicTransportPurpose, Unity.Entities.Entity entity);
    public Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity primaryPrefab, Unity.Entities.Entity secondaryPrefab, Game.Prefabs.TransportType transportType, Game.Vehicles.EnergyTypes energyTypes, Game.Vehicles.SizeClass sizeClass, Game.Prefabs.PublicTransportPurpose publicTransportPurpose, Game.Economy.Resource cargoResources, Unity.Mathematics.int2& passengerCapacity, Unity.Mathematics.int2& cargoCapacity, System.Boolean parked);
    public Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity primaryPrefab, Unity.Entities.Entity secondaryPrefab, Game.Prefabs.TransportType transportType, Game.Vehicles.EnergyTypes energyTypes, Game.Vehicles.SizeClass sizeClass, Game.Prefabs.PublicTransportPurpose publicTransportPurpose, Game.Economy.Resource cargoResources, Unity.Mathematics.int2& passengerCapacity, Unity.Mathematics.int2& cargoCapacity, System.Boolean parked, Unity.Collections.NativeList`1[[Game.Vehicles.LayoutElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& layout);
    private Unity.Entities.EntityArchetype GetArchetype(Unity.Entities.Entity prefab, System.Boolean controller, System.Boolean parked);
    public static Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    private Unity.Entities.Entity GetRandomVehicle(Unity.Mathematics.Random& random, Game.Prefabs.TransportType transportType, Game.Vehicles.EnergyTypes energyTypes, Game.Vehicles.SizeClass sizeClass, Game.Prefabs.PublicTransportPurpose publicTransportPurpose, Game.Economy.Resource cargoResources, Unity.Entities.Entity primaryPrefab, Unity.Entities.Entity secondaryPrefab, Unity.Collections.NativeList<Unity.Entities.Entity> primaryPrefabs, Unity.Collections.NativeList<Unity.Entities.Entity> secondaryPrefabs, System.Boolean ignoreTheme, System.Boolean& isMultipleUnitTrain, System.Int32& unitCount, Unity.Entities.Entity& secondaryResult, Unity.Mathematics.int2& passengerCapacity, Unity.Mathematics.int2& cargoCapacity);
    public System.Void ListVehicles(Game.Prefabs.TransportType transportType, Game.Vehicles.EnergyTypes energyTypes, Game.Vehicles.SizeClass sizeClass, Game.Prefabs.PublicTransportPurpose publicTransportPurpose, Game.Economy.Resource cargoResources, Unity.Collections.NativeList<Unity.Entities.Entity> primaryPrefabs, Unity.Collections.NativeList<Unity.Entities.Entity> secondaryPrefabs);
    private System.Boolean PickVehicle(Unity.Mathematics.Random& random, System.Int32 probability, System.Int32 priority, System.Int32& totalProbability, System.Int32& selectedPriority);
    public System.Void PostUpdate(Unity.Jobs.JobHandle jobHandle);
    public System.Void PreUpdate(Unity.Entities.SystemBase system, Game.City.CityConfigurationSystem cityConfigurationSystem, Unity.Entities.EntityQuery query, Unity.Collections.Allocator allocator, Unity.Jobs.JobHandle& jobHandle);
    public System.Void SelectVehicle(Unity.Mathematics.Random& random, Game.Prefabs.TransportType transportType, Game.Vehicles.EnergyTypes energyTypes, Game.Vehicles.SizeClass sizeClass, Game.Prefabs.PublicTransportPurpose publicTransportPurpose, Game.Economy.Resource cargoResources, Unity.Entities.Entity& primaryPrefab, Unity.Entities.Entity& secondaryPrefab, Unity.Mathematics.int2& passengerCapacity, Unity.Mathematics.int2& cargoCapacity);
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

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.PublicTransportVehicleData> m_PublicTransportVehicleType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.PublicTransportVehicleData> m_PublicTransportVehicleType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CargoTransportVehicleData> m_CargoTransportVehicleType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CargoTransportVehicleData> m_CargoTransportVehicleType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.TrainData> m_TrainType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.TrainData> m_TrainType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.TrainEngineData> m_TrainEngineType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.TrainEngineData> m_TrainEngineType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.TrainCarriageData> m_TrainCarriageType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.TrainCarriageData> m_TrainCarriageType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.MultipleUnitTrainData> m_MultipleUnitTrainType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.MultipleUnitTrainData> m_MultipleUnitTrainType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.TaxiData> m_TaxiType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.TaxiData> m_TaxiType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarData> m_CarType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarData> m_CarType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.AircraftData> m_AircraftType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.AircraftData> m_AircraftType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.AirplaneData> m_AirplaneType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.AirplaneData> m_AirplaneType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.HelicopterData> m_HelicopterType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.HelicopterData> m_HelicopterType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.WatercraftData> m_WatercraftType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.WatercraftData> m_WatercraftType;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.ObjectData> m_ObjectData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.ObjectData> m_ObjectData;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.MovingObjectData> m_MovingObjectData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.MovingObjectData> m_MovingObjectData;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.TrainObjectData> m_TrainObjectData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.TrainObjectData> m_TrainObjectData;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.PublicTransportVehicleData> m_PublicTransportVehicleData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.PublicTransportVehicleData> m_PublicTransportVehicleData;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.CargoTransportVehicleData> m_CargoTransportVehicleData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.CargoTransportVehicleData> m_CargoTransportVehicleData;
```

- `private Unity.Entities.BufferLookup<Game.Prefabs.VehicleCarriageElement> m_VehicleCarriages`  

```csharp
private Unity.Entities.BufferLookup<Game.Prefabs.VehicleCarriageElement> m_VehicleCarriages;
```


## Constructors

- `public TransportVehicleSelectData(Unity.Entities.SystemBase system)`  

```csharp
public TransportVehicleSelectData(Unity.Entities.SystemBase system);
```


## Methods

- `private AddTransportComponents(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Game.Prefabs.PublicTransportPurpose publicTransportPurpose, Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void AddTransportComponents(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Game.Prefabs.PublicTransportPurpose publicTransportPurpose, Unity.Entities.Entity entity);
```

- `public CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity primaryPrefab, Unity.Entities.Entity secondaryPrefab, Game.Prefabs.TransportType transportType, Game.Vehicles.EnergyTypes energyTypes, Game.Vehicles.SizeClass sizeClass, Game.Prefabs.PublicTransportPurpose publicTransportPurpose, Game.Economy.Resource cargoResources, Unity.Mathematics.int2& passengerCapacity, Unity.Mathematics.int2& cargoCapacity, System.Boolean parked) : Unity.Entities.Entity`  

```csharp
public Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity primaryPrefab, Unity.Entities.Entity secondaryPrefab, Game.Prefabs.TransportType transportType, Game.Vehicles.EnergyTypes energyTypes, Game.Vehicles.SizeClass sizeClass, Game.Prefabs.PublicTransportPurpose publicTransportPurpose, Game.Economy.Resource cargoResources, Unity.Mathematics.int2& passengerCapacity, Unity.Mathematics.int2& cargoCapacity, System.Boolean parked);
```

- `public CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity primaryPrefab, Unity.Entities.Entity secondaryPrefab, Game.Prefabs.TransportType transportType, Game.Vehicles.EnergyTypes energyTypes, Game.Vehicles.SizeClass sizeClass, Game.Prefabs.PublicTransportPurpose publicTransportPurpose, Game.Economy.Resource cargoResources, Unity.Mathematics.int2& passengerCapacity, Unity.Mathematics.int2& cargoCapacity, System.Boolean parked, Unity.Collections.NativeList`1[[Game.Vehicles.LayoutElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& layout) : Unity.Entities.Entity`  

```csharp
public Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity primaryPrefab, Unity.Entities.Entity secondaryPrefab, Game.Prefabs.TransportType transportType, Game.Vehicles.EnergyTypes energyTypes, Game.Vehicles.SizeClass sizeClass, Game.Prefabs.PublicTransportPurpose publicTransportPurpose, Game.Economy.Resource cargoResources, Unity.Mathematics.int2& passengerCapacity, Unity.Mathematics.int2& cargoCapacity, System.Boolean parked, Unity.Collections.NativeList`1[[Game.Vehicles.LayoutElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& layout);
```

- `private GetArchetype(Unity.Entities.Entity prefab, System.Boolean controller, System.Boolean parked) : Unity.Entities.EntityArchetype`  

```csharp
private Unity.Entities.EntityArchetype GetArchetype(Unity.Entities.Entity prefab, System.Boolean controller, System.Boolean parked);
```

- `public static GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public static Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
```

- `private GetRandomVehicle(Unity.Mathematics.Random& random, Game.Prefabs.TransportType transportType, Game.Vehicles.EnergyTypes energyTypes, Game.Vehicles.SizeClass sizeClass, Game.Prefabs.PublicTransportPurpose publicTransportPurpose, Game.Economy.Resource cargoResources, Unity.Entities.Entity primaryPrefab, Unity.Entities.Entity secondaryPrefab, Unity.Collections.NativeList<Unity.Entities.Entity> primaryPrefabs, Unity.Collections.NativeList<Unity.Entities.Entity> secondaryPrefabs, System.Boolean ignoreTheme, System.Boolean& isMultipleUnitTrain, System.Int32& unitCount, Unity.Entities.Entity& secondaryResult, Unity.Mathematics.int2& passengerCapacity, Unity.Mathematics.int2& cargoCapacity) : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity GetRandomVehicle(Unity.Mathematics.Random& random, Game.Prefabs.TransportType transportType, Game.Vehicles.EnergyTypes energyTypes, Game.Vehicles.SizeClass sizeClass, Game.Prefabs.PublicTransportPurpose publicTransportPurpose, Game.Economy.Resource cargoResources, Unity.Entities.Entity primaryPrefab, Unity.Entities.Entity secondaryPrefab, Unity.Collections.NativeList<Unity.Entities.Entity> primaryPrefabs, Unity.Collections.NativeList<Unity.Entities.Entity> secondaryPrefabs, System.Boolean ignoreTheme, System.Boolean& isMultipleUnitTrain, System.Int32& unitCount, Unity.Entities.Entity& secondaryResult, Unity.Mathematics.int2& passengerCapacity, Unity.Mathematics.int2& cargoCapacity);
```

- `public ListVehicles(Game.Prefabs.TransportType transportType, Game.Vehicles.EnergyTypes energyTypes, Game.Vehicles.SizeClass sizeClass, Game.Prefabs.PublicTransportPurpose publicTransportPurpose, Game.Economy.Resource cargoResources, Unity.Collections.NativeList<Unity.Entities.Entity> primaryPrefabs, Unity.Collections.NativeList<Unity.Entities.Entity> secondaryPrefabs) : System.Void`  

```csharp
public System.Void ListVehicles(Game.Prefabs.TransportType transportType, Game.Vehicles.EnergyTypes energyTypes, Game.Vehicles.SizeClass sizeClass, Game.Prefabs.PublicTransportPurpose publicTransportPurpose, Game.Economy.Resource cargoResources, Unity.Collections.NativeList<Unity.Entities.Entity> primaryPrefabs, Unity.Collections.NativeList<Unity.Entities.Entity> secondaryPrefabs);
```

- `private PickVehicle(Unity.Mathematics.Random& random, System.Int32 probability, System.Int32 priority, System.Int32& totalProbability, System.Int32& selectedPriority) : System.Boolean`  

```csharp
private System.Boolean PickVehicle(Unity.Mathematics.Random& random, System.Int32 probability, System.Int32 priority, System.Int32& totalProbability, System.Int32& selectedPriority);
```

- `public PostUpdate(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public System.Void PostUpdate(Unity.Jobs.JobHandle jobHandle);
```

- `public PreUpdate(Unity.Entities.SystemBase system, Game.City.CityConfigurationSystem cityConfigurationSystem, Unity.Entities.EntityQuery query, Unity.Collections.Allocator allocator, Unity.Jobs.JobHandle& jobHandle) : System.Void`  

```csharp
public System.Void PreUpdate(Unity.Entities.SystemBase system, Game.City.CityConfigurationSystem cityConfigurationSystem, Unity.Entities.EntityQuery query, Unity.Collections.Allocator allocator, Unity.Jobs.JobHandle& jobHandle);
```

- `public SelectVehicle(Unity.Mathematics.Random& random, Game.Prefabs.TransportType transportType, Game.Vehicles.EnergyTypes energyTypes, Game.Vehicles.SizeClass sizeClass, Game.Prefabs.PublicTransportPurpose publicTransportPurpose, Game.Economy.Resource cargoResources, Unity.Entities.Entity& primaryPrefab, Unity.Entities.Entity& secondaryPrefab, Unity.Mathematics.int2& passengerCapacity, Unity.Mathematics.int2& cargoCapacity) : System.Void`  

```csharp
public System.Void SelectVehicle(Unity.Mathematics.Random& random, Game.Prefabs.TransportType transportType, Game.Vehicles.EnergyTypes energyTypes, Game.Vehicles.SizeClass sizeClass, Game.Prefabs.PublicTransportPurpose publicTransportPurpose, Game.Economy.Resource cargoResources, Unity.Entities.Entity& primaryPrefab, Unity.Entities.Entity& secondaryPrefab, Unity.Mathematics.int2& passengerCapacity, Unity.Mathematics.int2& cargoCapacity);
```


