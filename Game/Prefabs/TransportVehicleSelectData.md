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
public TransportVehicleSelectData(SystemBase system)
	{
		m_PrefabChunks = default(NativeList<ArchetypeChunk>);
		m_RequirementData = new VehicleSelectRequirementData(system);
		m_EntityType = system.GetEntityTypeHandle();
		m_PublicTransportVehicleType = system.GetComponentTypeHandle<PublicTransportVehicleData>(isReadOnly: true);
		m_CargoTransportVehicleType = system.GetComponentTypeHandle<CargoTransportVehicleData>(isReadOnly: true);
		m_TrainType = system.GetComponentTypeHandle<TrainData>(isReadOnly: true);
		m_TrainEngineType = system.GetComponentTypeHandle<TrainEngineData>(isReadOnly: true);
		m_TrainCarriageType = system.GetComponentTypeHandle<TrainCarriageData>(isReadOnly: true);
		m_MultipleUnitTrainType = system.GetComponentTypeHandle<MultipleUnitTrainData>(isReadOnly: true);
		m_TaxiType = system.GetComponentTypeHandle<TaxiData>(isReadOnly: true);
		m_CarType = system.GetComponentTypeHandle<CarData>(isReadOnly: true);
		m_AircraftType = system.GetComponentTypeHandle<AircraftData>(isReadOnly: true);
		m_AirplaneType = system.GetComponentTypeHandle<AirplaneData>(isReadOnly: true);
		m_HelicopterType = system.GetComponentTypeHandle<HelicopterData>(isReadOnly: true);
		m_WatercraftType = system.GetComponentTypeHandle<WatercraftData>(isReadOnly: true);
		m_ObjectData = system.GetComponentLookup<ObjectData>(isReadOnly: true);
		m_MovingObjectData = system.GetComponentLookup<MovingObjectData>(isReadOnly: true);
		m_TrainObjectData = system.GetComponentLookup<TrainObjectData>(isReadOnly: true);
		m_PublicTransportVehicleData = system.GetComponentLookup<PublicTransportVehicleData>(isReadOnly: true);
		m_CargoTransportVehicleData = system.GetComponentLookup<CargoTransportVehicleData>(isReadOnly: true);
		m_VehicleCarriages = system.GetBufferLookup<VehicleCarriageElement>(isReadOnly: true);
	}
```


## Methods

- `private AddTransportComponents(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Game.Prefabs.PublicTransportPurpose publicTransportPurpose, Unity.Entities.Entity entity) : System.Void`  

```csharp
private void AddTransportComponents(EntityCommandBuffer.ParallelWriter commandBuffer, int jobIndex, PublicTransportPurpose publicTransportPurpose, Entity entity)
	{
		if ((publicTransportPurpose & PublicTransportPurpose.TransportLine) != 0)
		{
			commandBuffer.AddComponent(jobIndex, entity, default(PassengerTransport));
		}
		if ((publicTransportPurpose & PublicTransportPurpose.Evacuation) != 0)
		{
			commandBuffer.AddComponent(jobIndex, entity, default(EvacuatingTransport));
		}
		if ((publicTransportPurpose & PublicTransportPurpose.PrisonerTransport) != 0)
		{
			commandBuffer.AddComponent(jobIndex, entity, default(PrisonerTransport));
		}
	}
```

- `public CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity primaryPrefab, Unity.Entities.Entity secondaryPrefab, Game.Prefabs.TransportType transportType, Game.Vehicles.EnergyTypes energyTypes, Game.Vehicles.SizeClass sizeClass, Game.Prefabs.PublicTransportPurpose publicTransportPurpose, Game.Economy.Resource cargoResources, Unity.Mathematics.int2& passengerCapacity, Unity.Mathematics.int2& cargoCapacity, System.Boolean parked) : Unity.Entities.Entity`  

```csharp
public Entity CreateVehicle(EntityCommandBuffer.ParallelWriter commandBuffer, int jobIndex, ref Random random, Transform transform, Entity source, Entity primaryPrefab, Entity secondaryPrefab, TransportType transportType, EnergyTypes energyTypes, SizeClass sizeClass, PublicTransportPurpose publicTransportPurpose, Resource cargoResources, ref int2 passengerCapacity, ref int2 cargoCapacity, bool parked, ref NativeList<LayoutElement> layout)
	{
		primaryPrefab = GetRandomVehicle(ref random, transportType, energyTypes, sizeClass, publicTransportPurpose, cargoResources, primaryPrefab, secondaryPrefab, default(NativeList<Entity>), default(NativeList<Entity>), ignoreTheme: false, out var isMultipleUnitTrain, out var unitCount, out var secondaryResult, ref passengerCapacity, ref cargoCapacity);
		secondaryPrefab = secondaryResult;
		if (primaryPrefab == Entity.Null)
		{
			return Entity.Null;
		}
		Entity entity = ((transportType != TransportType.Train && transportType != TransportType.Tram && transportType != TransportType.Subway) ? commandBuffer.CreateEntity(jobIndex, GetArchetype(primaryPrefab, controller: false, parked)) : commandBuffer.CreateEntity(jobIndex, GetArchetype(primaryPrefab, controller: true, parked)));
		commandBuffer.SetComponent(jobIndex, entity, transform);
		commandBuffer.SetComponent(jobIndex, entity, new PrefabRef(primaryPrefab));
		commandBuffer.SetComponent(jobIndex, entity, new PseudoRandomSeed(ref random));
		AddTransportComponents(commandBuffer, jobIndex, publicTransportPurpose, entity);
		if (!parked && source != Entity.Null)
		{
			commandBuffer.AddComponent(jobIndex, entity, new TripSource(source));
			commandBuffer.AddComponent(jobIndex, entity, default(Unspawned));
		}
		bool flag = false;
		if (transportType == TransportType.Train || transportType == TransportType.Tram || transportType == TransportType.Subway)
		{
			commandBuffer.SetComponent(jobIndex, entity, new Controller(entity));
			flag = true;
			if (layout.IsCreated)
			{
				layout.Clear();
			}
			else
			{
				layout = new NativeList<LayoutElement>(32, Allocator.Temp);
			}
		}
		if (flag)
		{
			int num = 0;
			if (isMultipleUnitTrain)
			{
				layout.Add(new LayoutElement(entity));
			}
			Entity entity2 = (isMultipleUnitTrain ? primaryPrefab : secondaryPrefab);
			if (entity2 != Entity.Null)
			{
				EntityArchetype archetype = GetArchetype(entity2, controller: false, parked);
				for (int i = 0; i < unitCount; i++)
				{
					if (!isMultipleUnitTrain || i != 0)
					{
						Game.Vehicles.TrainFlags trainFlags = (Game.Vehicles.TrainFlags)0u;
						if (!isMultipleUnitTrain && i != 0 && random.NextBool())
						{
							trainFlags |= Game.Vehicles.TrainFlags.Reversed;
						}
						Entity entity3 = commandBuffer.CreateEntity(jobIndex, archetype);
						commandBuffer.SetComponent(jobIndex, entity3, transform);
						commandBuffer.SetComponent(jobIndex, entity3, new PrefabRef(entity2));
						commandBuffer.SetComponent(jobIndex, entity3, new Controller(entity));
						commandBuffer.SetComponent(jobIndex, entity3, new Train(trainFlags));
						commandBuffer.SetComponent(jobIndex, entity3, new PseudoRandomSeed(ref random));
						AddTransportComponents(commandBuffer, jobIndex, publicTransportPurpose, entity3);
						if (!parked && source != Entity.Null)
						{
							commandBuffer.AddComponent(jobIndex, entity3, new TripSource(source));
							commandBuffer.AddComponent(jobIndex, entity3, default(Unspawned));
						}
						layout.Add(new LayoutElement(entity3));
					}
					if (!m_VehicleCarriages.HasBuffer(entity2))
					{
						continue;
					}
					DynamicBuffer<VehicleCarriageElement> dynamicBuffer = m_VehicleCarriages[entity2];
					for (int j = 0; j < dynamicBuffer.Length; j++)
					{
						VehicleCarriageElement vehicleCarriageElement = dynamicBuffer[j];
						if (vehicleCarriageElement.m_Prefab == Entity.Null)
						{
							num += vehicleCarriageElement.m_Count.x;
							continue;
						}
						EntityArchetype archetype2 = GetArchetype(vehicleCarriageElement.m_Prefab, controller: false, parked);
						for (int k = 0; k < vehicleCarriageElement.m_Count.x; k++)
						{
							Game.Vehicles.TrainFlags trainFlags2 = (Game.Vehicles.TrainFlags)0u;
							switch (vehicleCarriageElement.m_Direction)
							{
							case VehicleCarriageDirection.Reversed:
								trainFlags2 |= Game.Vehicles.TrainFlags.Reversed;
								break;
							case VehicleCarriageDirection.Random:
								if (random.NextBool())
								{
									trainFlags2 |= Game.Vehicles.TrainFlags.Reversed;
								}
								break;
							}
							Entity entity4 = commandBuffer.CreateEntity(jobIndex, archetype2);
							commandBuffer.SetComponent(jobIndex, entity4, transform);
							commandBuffer.SetComponent(jobIndex, entity4, new PrefabRef(vehicleCarriageElement.m_Prefab));
							commandBuffer.SetComponent(jobIndex, entity4, new Controller(entity));
							commandBuffer.SetComponent(jobIndex, entity4, new Train(trainFlags2));
							commandBuffer.SetComponent(jobIndex, entity4, new PseudoRandomSeed(ref random));
							AddTransportComponents(commandBuffer, jobIndex, publicTransportPurpose, entity4);
							if (!parked && source != Entity.Null)
							{
								commandBuffer.AddComponent(jobIndex, entity4, new TripSource(source));
								commandBuffer.AddComponent(jobIndex, entity4, default(Unspawned));
							}
							layout.Add(new LayoutElement(entity4));
						}
					}
				}
			}
			if (!isMultipleUnitTrain)
			{
				layout.Add(new LayoutElement(entity));
				num--;
			}
			if (num > 0)
			{
				EntityArchetype archetype3 = GetArchetype(primaryPrefab, controller: false, parked);
				for (int l = 0; l < num; l++)
				{
					Game.Vehicles.TrainFlags trainFlags3 = (Game.Vehicles.TrainFlags)0u;
					if (random.NextBool())
					{
						trainFlags3 |= Game.Vehicles.TrainFlags.Reversed;
					}
					Entity entity5 = commandBuffer.CreateEntity(jobIndex, archetype3);
					commandBuffer.SetComponent(jobIndex, entity5, transform);
					commandBuffer.SetComponent(jobIndex, entity5, new PrefabRef(primaryPrefab));
					commandBuffer.SetComponent(jobIndex, entity5, new Controller(entity));
					commandBuffer.SetComponent(jobIndex, entity5, new Train(trainFlags3));
					commandBuffer.SetComponent(jobIndex, entity5, new PseudoRandomSeed(ref random));
					AddTransportComponents(commandBuffer, jobIndex, publicTransportPurpose, entity5);
					if (!parked && source != Entity.Null)
					{
						commandBuffer.AddComponent(jobIndex, entity5, new TripSource(source));
						commandBuffer.AddComponent(jobIndex, entity5, default(Unspawned));
					}
					layout.Add(new LayoutElement(entity5));
				}
			}
			commandBuffer.SetBuffer<LayoutElement>(jobIndex, entity).CopyFrom(layout.AsArray());
		}
		return entity;
	}
```

- `public CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity primaryPrefab, Unity.Entities.Entity secondaryPrefab, Game.Prefabs.TransportType transportType, Game.Vehicles.EnergyTypes energyTypes, Game.Vehicles.SizeClass sizeClass, Game.Prefabs.PublicTransportPurpose publicTransportPurpose, Game.Economy.Resource cargoResources, Unity.Mathematics.int2& passengerCapacity, Unity.Mathematics.int2& cargoCapacity, System.Boolean parked, Unity.Collections.NativeList`1[[Game.Vehicles.LayoutElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& layout) : Unity.Entities.Entity`  

```csharp
public Entity CreateVehicle(EntityCommandBuffer.ParallelWriter commandBuffer, int jobIndex, ref Random random, Transform transform, Entity source, Entity primaryPrefab, Entity secondaryPrefab, TransportType transportType, EnergyTypes energyTypes, SizeClass sizeClass, PublicTransportPurpose publicTransportPurpose, Resource cargoResources, ref int2 passengerCapacity, ref int2 cargoCapacity, bool parked, ref NativeList<LayoutElement> layout)
	{
		primaryPrefab = GetRandomVehicle(ref random, transportType, energyTypes, sizeClass, publicTransportPurpose, cargoResources, primaryPrefab, secondaryPrefab, default(NativeList<Entity>), default(NativeList<Entity>), ignoreTheme: false, out var isMultipleUnitTrain, out var unitCount, out var secondaryResult, ref passengerCapacity, ref cargoCapacity);
		secondaryPrefab = secondaryResult;
		if (primaryPrefab == Entity.Null)
		{
			return Entity.Null;
		}
		Entity entity = ((transportType != TransportType.Train && transportType != TransportType.Tram && transportType != TransportType.Subway) ? commandBuffer.CreateEntity(jobIndex, GetArchetype(primaryPrefab, controller: false, parked)) : commandBuffer.CreateEntity(jobIndex, GetArchetype(primaryPrefab, controller: true, parked)));
		commandBuffer.SetComponent(jobIndex, entity, transform);
		commandBuffer.SetComponent(jobIndex, entity, new PrefabRef(primaryPrefab));
		commandBuffer.SetComponent(jobIndex, entity, new PseudoRandomSeed(ref random));
		AddTransportComponents(commandBuffer, jobIndex, publicTransportPurpose, entity);
		if (!parked && source != Entity.Null)
		{
			commandBuffer.AddComponent(jobIndex, entity, new TripSource(source));
			commandBuffer.AddComponent(jobIndex, entity, default(Unspawned));
		}
		bool flag = false;
		if (transportType == TransportType.Train || transportType == TransportType.Tram || transportType == TransportType.Subway)
		{
			commandBuffer.SetComponent(jobIndex, entity, new Controller(entity));
			flag = true;
			if (layout.IsCreated)
			{
				layout.Clear();
			}
			else
			{
				layout = new NativeList<LayoutElement>(32, Allocator.Temp);
			}
		}
		if (flag)
		{
			int num = 0;
			if (isMultipleUnitTrain)
			{
				layout.Add(new LayoutElement(entity));
			}
			Entity entity2 = (isMultipleUnitTrain ? primaryPrefab : secondaryPrefab);
			if (entity2 != Entity.Null)
			{
				EntityArchetype archetype = GetArchetype(entity2, controller: false, parked);
				for (int i = 0; i < unitCount; i++)
				{
					if (!isMultipleUnitTrain || i != 0)
					{
						Game.Vehicles.TrainFlags trainFlags = (Game.Vehicles.TrainFlags)0u;
						if (!isMultipleUnitTrain && i != 0 && random.NextBool())
						{
							trainFlags |= Game.Vehicles.TrainFlags.Reversed;
						}
						Entity entity3 = commandBuffer.CreateEntity(jobIndex, archetype);
						commandBuffer.SetComponent(jobIndex, entity3, transform);
						commandBuffer.SetComponent(jobIndex, entity3, new PrefabRef(entity2));
						commandBuffer.SetComponent(jobIndex, entity3, new Controller(entity));
						commandBuffer.SetComponent(jobIndex, entity3, new Train(trainFlags));
						commandBuffer.SetComponent(jobIndex, entity3, new PseudoRandomSeed(ref random));
						AddTransportComponents(commandBuffer, jobIndex, publicTransportPurpose, entity3);
						if (!parked && source != Entity.Null)
						{
							commandBuffer.AddComponent(jobIndex, entity3, new TripSource(source));
							commandBuffer.AddComponent(jobIndex, entity3, default(Unspawned));
						}
						layout.Add(new LayoutElement(entity3));
					}
					if (!m_VehicleCarriages.HasBuffer(entity2))
					{
						continue;
					}
					DynamicBuffer<VehicleCarriageElement> dynamicBuffer = m_VehicleCarriages[entity2];
					for (int j = 0; j < dynamicBuffer.Length; j++)
					{
						VehicleCarriageElement vehicleCarriageElement = dynamicBuffer[j];
						if (vehicleCarriageElement.m_Prefab == Entity.Null)
						{
							num += vehicleCarriageElement.m_Count.x;
							continue;
						}
						EntityArchetype archetype2 = GetArchetype(vehicleCarriageElement.m_Prefab, controller: false, parked);
						for (int k = 0; k < vehicleCarriageElement.m_Count.x; k++)
						{
							Game.Vehicles.TrainFlags trainFlags2 = (Game.Vehicles.TrainFlags)0u;
							switch (vehicleCarriageElement.m_Direction)
							{
							case VehicleCarriageDirection.Reversed:
								trainFlags2 |= Game.Vehicles.TrainFlags.Reversed;
								break;
							case VehicleCarriageDirection.Random:
								if (random.NextBool())
								{
									trainFlags2 |= Game.Vehicles.TrainFlags.Reversed;
								}
								break;
							}
							Entity entity4 = commandBuffer.CreateEntity(jobIndex, archetype2);
							commandBuffer.SetComponent(jobIndex, entity4, transform);
							commandBuffer.SetComponent(jobIndex, entity4, new PrefabRef(vehicleCarriageElement.m_Prefab));
							commandBuffer.SetComponent(jobIndex, entity4, new Controller(entity));
							commandBuffer.SetComponent(jobIndex, entity4, new Train(trainFlags2));
							commandBuffer.SetComponent(jobIndex, entity4, new PseudoRandomSeed(ref random));
							AddTransportComponents(commandBuffer, jobIndex, publicTransportPurpose, entity4);
							if (!parked && source != Entity.Null)
							{
								commandBuffer.AddComponent(jobIndex, entity4, new TripSource(source));
								commandBuffer.AddComponent(jobIndex, entity4, default(Unspawned));
							}
							layout.Add(new LayoutElement(entity4));
						}
					}
				}
			}
			if (!isMultipleUnitTrain)
			{
				layout.Add(new LayoutElement(entity));
				num--;
			}
			if (num > 0)
			{
				EntityArchetype archetype3 = GetArchetype(primaryPrefab, controller: false, parked);
				for (int l = 0; l < num; l++)
				{
					Game.Vehicles.TrainFlags trainFlags3 = (Game.Vehicles.TrainFlags)0u;
					if (random.NextBool())
					{
						trainFlags3 |= Game.Vehicles.TrainFlags.Reversed;
					}
					Entity entity5 = commandBuffer.CreateEntity(jobIndex, archetype3);
					commandBuffer.SetComponent(jobIndex, entity5, transform);
					commandBuffer.SetComponent(jobIndex, entity5, new PrefabRef(primaryPrefab));
					commandBuffer.SetComponent(jobIndex, entity5, new Controller(entity));
					commandBuffer.SetComponent(jobIndex, entity5, new Train(trainFlags3));
					commandBuffer.SetComponent(jobIndex, entity5, new PseudoRandomSeed(ref random));
					AddTransportComponents(commandBuffer, jobIndex, publicTransportPurpose, entity5);
					if (!parked && source != Entity.Null)
					{
						commandBuffer.AddComponent(jobIndex, entity5, new TripSource(source));
						commandBuffer.AddComponent(jobIndex, entity5, default(Unspawned));
					}
					layout.Add(new LayoutElement(entity5));
				}
			}
			commandBuffer.SetBuffer<LayoutElement>(jobIndex, entity).CopyFrom(layout.AsArray());
		}
		return entity;
	}
```

- `private GetArchetype(Unity.Entities.Entity prefab, System.Boolean controller, System.Boolean parked) : Unity.Entities.EntityArchetype`  

```csharp
private EntityArchetype GetArchetype(Entity prefab, bool controller, bool parked)
	{
		if (controller)
		{
			TrainObjectData trainObjectData = m_TrainObjectData[prefab];
			if (!parked)
			{
				return trainObjectData.m_ControllerArchetype;
			}
			return trainObjectData.m_StoppedControllerArchetype;
		}
		if (parked)
		{
			return m_MovingObjectData[prefab].m_StoppedArchetype;
		}
		return m_ObjectData[prefab].m_Archetype;
	}
```

- `public static GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public static EntityQueryDesc GetEntityQueryDesc()
	{
		EntityQueryDesc entityQueryDesc = new EntityQueryDesc();
		entityQueryDesc.All = new ComponentType[3]
		{
			ComponentType.ReadOnly<VehicleData>(),
			ComponentType.ReadOnly<ObjectData>(),
			ComponentType.ReadOnly<PrefabData>()
		};
		entityQueryDesc.Any = new ComponentType[4]
		{
			ComponentType.ReadOnly<PublicTransportVehicleData>(),
			ComponentType.ReadOnly<CargoTransportVehicleData>(),
			ComponentType.ReadOnly<TrainEngineData>(),
			ComponentType.ReadOnly<TaxiData>()
		};
		entityQueryDesc.None = new ComponentType[1] { ComponentType.ReadOnly<Locked>() };
		return entityQueryDesc;
	}
```

- `private GetRandomVehicle(Unity.Mathematics.Random& random, Game.Prefabs.TransportType transportType, Game.Vehicles.EnergyTypes energyTypes, Game.Vehicles.SizeClass sizeClass, Game.Prefabs.PublicTransportPurpose publicTransportPurpose, Game.Economy.Resource cargoResources, Unity.Entities.Entity primaryPrefab, Unity.Entities.Entity secondaryPrefab, Unity.Collections.NativeList<Unity.Entities.Entity> primaryPrefabs, Unity.Collections.NativeList<Unity.Entities.Entity> secondaryPrefabs, System.Boolean ignoreTheme, System.Boolean& isMultipleUnitTrain, System.Int32& unitCount, Unity.Entities.Entity& secondaryResult, Unity.Mathematics.int2& passengerCapacity, Unity.Mathematics.int2& cargoCapacity) : Unity.Entities.Entity`  

```csharp
private Entity GetRandomVehicle(ref Random random, TransportType transportType, EnergyTypes energyTypes, SizeClass sizeClass, PublicTransportPurpose publicTransportPurpose, Resource cargoResources, Entity primaryPrefab, Entity secondaryPrefab, NativeList<Entity> primaryPrefabs, NativeList<Entity> secondaryPrefabs, bool ignoreTheme, out bool isMultipleUnitTrain, out int unitCount, out Entity secondaryResult, ref int2 passengerCapacity, ref int2 cargoCapacity)
	{
		Entity entity = Entity.Null;
		secondaryResult = Entity.Null;
		int2 @int = 0;
		int2 int2 = 0;
		isMultipleUnitTrain = false;
		unitCount = 1;
		int num = 1;
		TrackTypes trackTypes = TrackTypes.None;
		HelicopterType helicopterType = HelicopterType.Helicopter;
		switch (transportType)
		{
		case TransportType.Train:
			trackTypes = TrackTypes.Train;
			break;
		case TransportType.Tram:
			trackTypes = TrackTypes.Tram;
			break;
		case TransportType.Subway:
			trackTypes = TrackTypes.Subway;
			break;
		case TransportType.Helicopter:
			helicopterType = HelicopterType.Helicopter;
			break;
		case TransportType.Rocket:
			helicopterType = HelicopterType.Rocket;
			break;
		}
		for (int i = 0; i < m_PrefabChunks.Length; i++)
		{
			ArchetypeChunk chunk = m_PrefabChunks[i];
			switch (transportType)
			{
			case TransportType.Bus:
			{
				NativeArray<CarData> nativeArray18 = chunk.GetNativeArray(ref m_CarType);
				if (nativeArray18.Length == 0)
				{
					break;
				}
				NativeArray<Entity> nativeArray19 = chunk.GetNativeArray(m_EntityType);
				NativeArray<PublicTransportVehicleData> nativeArray20 = chunk.GetNativeArray(ref m_PublicTransportVehicleType);
				if (nativeArray20.Length == 0)
				{
					break;
				}
				VehicleSelectRequirementData.Chunk chunk6 = m_RequirementData.GetChunk(chunk);
				for (int num6 = 0; num6 < nativeArray18.Length; num6++)
				{
					if ((nativeArray20[num6].m_PurposeMask & publicTransportPurpose) == 0)
					{
						continue;
					}
					CarData carData2 = nativeArray18[num6];
					if ((carData2.m_EnergyType != EnergyTypes.None && (carData2.m_EnergyType & energyTypes) == 0) || carData2.m_SizeClass != sizeClass)
					{
						continue;
					}
					Entity value6 = nativeArray19[num6];
					if (m_RequirementData.CheckRequirements(ref chunk6, num6, ignoreTheme || value6 == primaryPrefab))
					{
						int num7 = math.select(0, 2, value6 == primaryPrefab);
						num7 += math.select(0, 1, (carData2.m_EnergyType & EnergyTypes.Fuel) != 0);
						if (primaryPrefabs.IsCreated)
						{
							primaryPrefabs.Add(in value6);
						}
						if (PickVehicle(ref random, 100, num7, ref @int.x, ref int2.x))
						{
							entity = value6;
							passengerCapacity = nativeArray20[num6].m_PassengerCapacity;
						}
					}
				}
				break;
			}
			case TransportType.Train:
			case TransportType.Tram:
			case TransportType.Subway:
			{
				NativeArray<TrainData> nativeArray10 = chunk.GetNativeArray(ref m_TrainType);
				if (nativeArray10.Length == 0)
				{
					break;
				}
				NativeArray<Entity> nativeArray11 = chunk.GetNativeArray(m_EntityType);
				NativeArray<TrainEngineData> nativeArray12 = chunk.GetNativeArray(ref m_TrainEngineType);
				NativeArray<PublicTransportVehicleData> nativeArray13 = chunk.GetNativeArray(ref m_PublicTransportVehicleType);
				NativeArray<CargoTransportVehicleData> nativeArray14 = chunk.GetNativeArray(ref m_CargoTransportVehicleType);
				bool flag = nativeArray12.Length != 0;
				bool flag2 = chunk.Has(ref m_TrainCarriageType);
				bool flag3 = chunk.Has(ref m_MultipleUnitTrainType);
				VehicleSelectRequirementData.Chunk chunk4 = m_RequirementData.GetChunk(chunk);
				if ((flag && flag3) || (flag2 && !flag3))
				{
					if (publicTransportPurpose != (PublicTransportPurpose)0 != (nativeArray13.Length != 0) || cargoResources != Resource.NoResource != (nativeArray14.Length != 0))
					{
						break;
					}
					for (int l = 0; l < nativeArray10.Length; l++)
					{
						if ((publicTransportPurpose != 0 && (nativeArray13[l].m_PurposeMask & publicTransportPurpose) == 0) || (cargoResources != Resource.NoResource && (nativeArray14[l].m_Resources & cargoResources) == Resource.NoResource))
						{
							continue;
						}
						TrainData trainData = nativeArray10[l];
						if ((trainData.m_EnergyType != EnergyTypes.None && (trainData.m_EnergyType & energyTypes) == 0) || trainData.m_TrackType != trackTypes)
						{
							continue;
						}
						Entity value3 = nativeArray11[l];
						if (!m_RequirementData.CheckRequirements(ref chunk4, l, ignoreTheme || value3 == primaryPrefab))
						{
							continue;
						}
						int num3 = math.select(0, 2, value3 == primaryPrefab);
						num3 += math.select(0, 1, (trainData.m_EnergyType & EnergyTypes.Fuel) != 0);
						if (primaryPrefabs.IsCreated)
						{
							primaryPrefabs.Add(in value3);
						}
						if (PickVehicle(ref random, 100, num3, ref @int.x, ref int2.x))
						{
							isMultipleUnitTrain = flag3;
							if (flag)
							{
								unitCount = nativeArray12[l].m_Count.x;
							}
							entity = value3;
							if (publicTransportPurpose != 0)
							{
								passengerCapacity = nativeArray13[l].m_PassengerCapacity;
							}
							if (cargoResources != Resource.NoResource)
							{
								cargoCapacity = nativeArray14[l].m_CargoCapacity;
							}
						}
					}
				}
				else
				{
					if (!flag || flag3)
					{
						break;
					}
					for (int m = 0; m < nativeArray10.Length; m++)
					{
						TrainData trainData2 = nativeArray10[m];
						if ((trainData2.m_EnergyType != EnergyTypes.None && (trainData2.m_EnergyType & energyTypes) == 0) || trainData2.m_TrackType != trackTypes)
						{
							continue;
						}
						Entity value4 = nativeArray11[m];
						if (m_RequirementData.CheckRequirements(ref chunk4, m, ignoreTheme || value4 == secondaryPrefab))
						{
							int num4 = math.select(0, 2, value4 == secondaryPrefab);
							num4 += math.select(0, 1, (trainData2.m_EnergyType & EnergyTypes.Fuel) != 0);
							if (secondaryPrefabs.IsCreated)
							{
								secondaryPrefabs.Add(in value4);
							}
							if (PickVehicle(ref random, 100, num4, ref @int.y, ref int2.y))
							{
								num = nativeArray12[m].m_Count.x;
								secondaryResult = value4;
							}
						}
					}
				}
				break;
			}
			case TransportType.Taxi:
			{
				NativeArray<CarData> nativeArray15 = chunk.GetNativeArray(ref m_CarType);
				if (nativeArray15.Length == 0)
				{
					break;
				}
				NativeArray<Entity> nativeArray16 = chunk.GetNativeArray(m_EntityType);
				NativeArray<TaxiData> nativeArray17 = chunk.GetNativeArray(ref m_TaxiType);
				if (nativeArray17.Length == 0)
				{
					break;
				}
				VehicleSelectRequirementData.Chunk chunk5 = m_RequirementData.GetChunk(chunk);
				for (int n = 0; n < nativeArray15.Length; n++)
				{
					CarData carData = nativeArray15[n];
					if ((carData.m_EnergyType != EnergyTypes.None && (carData.m_EnergyType & energyTypes) == 0) || carData.m_SizeClass != sizeClass)
					{
						continue;
					}
					Entity value5 = nativeArray16[n];
					if (m_RequirementData.CheckRequirements(ref chunk5, n, ignoreTheme || value5 == primaryPrefab))
					{
						int num5 = math.select(0, 2, value5 == primaryPrefab);
						num5 += math.select(0, 1, (carData.m_EnergyType & EnergyTypes.Electricity) != 0);
						if (primaryPrefabs.IsCreated)
						{
							primaryPrefabs.Add(in value5);
						}
						if (PickVehicle(ref random, 100, num5, ref @int.x, ref int2.x))
						{
							entity = value5;
							passengerCapacity = nativeArray17[n].m_PassengerCapacity;
						}
					}
				}
				break;
			}
			case TransportType.Ship:
			{
				NativeArray<WatercraftData> nativeArray6 = chunk.GetNativeArray(ref m_WatercraftType);
				if (nativeArray6.Length == 0)
				{
					break;
				}
				NativeArray<Entity> nativeArray7 = chunk.GetNativeArray(m_EntityType);
				NativeArray<PublicTransportVehicleData> nativeArray8 = chunk.GetNativeArray(ref m_PublicTransportVehicleType);
				NativeArray<CargoTransportVehicleData> nativeArray9 = chunk.GetNativeArray(ref m_CargoTransportVehicleType);
				if (publicTransportPurpose != (PublicTransportPurpose)0 != (nativeArray8.Length != 0) || cargoResources != Resource.NoResource != (nativeArray9.Length != 0))
				{
					break;
				}
				VehicleSelectRequirementData.Chunk chunk3 = m_RequirementData.GetChunk(chunk);
				for (int k = 0; k < nativeArray6.Length; k++)
				{
					WatercraftData watercraftData = nativeArray6[k];
					if ((watercraftData.m_EnergyType != EnergyTypes.None && (watercraftData.m_EnergyType & energyTypes) == 0) || watercraftData.m_SizeClass != sizeClass || (publicTransportPurpose != 0 && (nativeArray8[k].m_PurposeMask & publicTransportPurpose) == 0) || (cargoResources != Resource.NoResource && (nativeArray9[k].m_Resources & cargoResources) == Resource.NoResource))
					{
						continue;
					}
					Entity value2 = nativeArray7[k];
					if (!m_RequirementData.CheckRequirements(ref chunk3, k, ignoreTheme || value2 == primaryPrefab))
					{
						continue;
					}
					int num2 = math.select(0, 2, value2 == primaryPrefab);
					num2 += math.select(0, 1, (watercraftData.m_EnergyType & EnergyTypes.Fuel) != 0);
					if (primaryPrefabs.IsCreated)
					{
						primaryPrefabs.Add(in value2);
					}
					if (PickVehicle(ref random, 100, num2, ref @int.x, ref int2.x))
					{
						entity = value2;
						if (publicTransportPurpose != 0)
						{
							passengerCapacity = nativeArray8[k].m_PassengerCapacity;
						}
						if (cargoResources != Resource.NoResource)
						{
							cargoCapacity = nativeArray9[k].m_CargoCapacity;
						}
					}
				}
				break;
			}
			case TransportType.Airplane:
			{
				if (!chunk.Has(ref m_AirplaneType))
				{
					break;
				}
				NativeArray<Entity> nativeArray21 = chunk.GetNativeArray(m_EntityType);
				NativeArray<AircraftData> nativeArray22 = chunk.GetNativeArray(ref m_AircraftType);
				NativeArray<PublicTransportVehicleData> nativeArray23 = chunk.GetNativeArray(ref m_PublicTransportVehicleType);
				NativeArray<CargoTransportVehicleData> nativeArray24 = chunk.GetNativeArray(ref m_CargoTransportVehicleType);
				if (publicTransportPurpose != (PublicTransportPurpose)0 != (nativeArray23.Length != 0) || cargoResources != Resource.NoResource != (nativeArray24.Length != 0))
				{
					break;
				}
				VehicleSelectRequirementData.Chunk chunk7 = m_RequirementData.GetChunk(chunk);
				for (int num8 = 0; num8 < nativeArray22.Length; num8++)
				{
					if (nativeArray22[num8].m_SizeClass != sizeClass || (publicTransportPurpose != 0 && (nativeArray23[num8].m_PurposeMask & publicTransportPurpose) == 0) || (cargoResources != Resource.NoResource && (nativeArray24[num8].m_Resources & cargoResources) == Resource.NoResource))
					{
						continue;
					}
					Entity value7 = nativeArray21[num8];
					if (!m_RequirementData.CheckRequirements(ref chunk7, num8, ignoreTheme || value7 == primaryPrefab))
					{
						continue;
					}
					int priority2 = math.select(0, 2, value7 == primaryPrefab);
					if (primaryPrefabs.IsCreated)
					{
						primaryPrefabs.Add(in value7);
					}
					if (PickVehicle(ref random, 100, priority2, ref @int.x, ref int2.x))
					{
						entity = value7;
						if (publicTransportPurpose != 0)
						{
							passengerCapacity = nativeArray23[num8].m_PassengerCapacity;
						}
						if (cargoResources != Resource.NoResource)
						{
							cargoCapacity = nativeArray24[num8].m_CargoCapacity;
						}
					}
				}
				break;
			}
			case TransportType.Helicopter:
			case TransportType.Rocket:
			{
				NativeArray<HelicopterData> nativeArray = chunk.GetNativeArray(ref m_HelicopterType);
				if (nativeArray.Length == 0)
				{
					break;
				}
				NativeArray<Entity> nativeArray2 = chunk.GetNativeArray(m_EntityType);
				NativeArray<AircraftData> nativeArray3 = chunk.GetNativeArray(ref m_AircraftType);
				NativeArray<PublicTransportVehicleData> nativeArray4 = chunk.GetNativeArray(ref m_PublicTransportVehicleType);
				NativeArray<CargoTransportVehicleData> nativeArray5 = chunk.GetNativeArray(ref m_CargoTransportVehicleType);
				if (publicTransportPurpose != (PublicTransportPurpose)0 != (nativeArray4.Length != 0) || cargoResources != Resource.NoResource != (nativeArray5.Length != 0))
				{
					break;
				}
				VehicleSelectRequirementData.Chunk chunk2 = m_RequirementData.GetChunk(chunk);
				for (int j = 0; j < nativeArray2.Length; j++)
				{
					if (nativeArray3[j].m_SizeClass != sizeClass || (publicTransportPurpose != 0 && (nativeArray4[j].m_PurposeMask & publicTransportPurpose) == 0) || (cargoResources != Resource.NoResource && (nativeArray5[j].m_Resources & cargoResources) == Resource.NoResource) || nativeArray[j].m_HelicopterType != helicopterType)
					{
						continue;
					}
					Entity value = nativeArray2[j];
					if (!m_RequirementData.CheckRequirements(ref chunk2, j, ignoreTheme || value == primaryPrefab))
					{
						continue;
					}
					int priority = math.select(0, 2, value == primaryPrefab);
					if (primaryPrefabs.IsCreated)
					{
						primaryPrefabs.Add(in value);
					}
					if (PickVehicle(ref random, 100, priority, ref @int.x, ref int2.x))
					{
						entity = value;
						if (publicTransportPurpose != 0)
						{
							passengerCapacity = nativeArray4[j].m_PassengerCapacity;
						}
						if (cargoResources != Resource.NoResource)
						{
							cargoCapacity = nativeArray5[j].m_CargoCapacity;
						}
					}
				}
				break;
			}
			}
		}
		if (isMultipleUnitTrain)
		{
			secondaryResult = Entity.Null;
		}
		else
		{
			unitCount = num;
		}
		bool flag4 = false;
		if (transportType == TransportType.Train || transportType == TransportType.Tram || transportType == TransportType.Subway)
		{
			flag4 = true;
		}
		if (flag4)
		{
			passengerCapacity.y = 0;
			cargoCapacity.y = 0;
			int num9 = 0;
			if (isMultipleUnitTrain)
			{
				passengerCapacity.y += passengerCapacity.x;
				cargoCapacity.y += cargoCapacity.x;
			}
			Entity entity2 = (isMultipleUnitTrain ? entity : secondaryResult);
			if (entity2 != Entity.Null)
			{
				for (int num10 = 0; num10 < unitCount; num10++)
				{
					if (isMultipleUnitTrain && num10 != 0)
					{
						passengerCapacity.y += passengerCapacity.x;
						cargoCapacity.y += cargoCapacity.x;
					}
					if (!m_VehicleCarriages.HasBuffer(entity2))
					{
						continue;
					}
					DynamicBuffer<VehicleCarriageElement> dynamicBuffer = m_VehicleCarriages[entity2];
					for (int num11 = 0; num11 < dynamicBuffer.Length; num11++)
					{
						VehicleCarriageElement vehicleCarriageElement = dynamicBuffer[num11];
						if (vehicleCarriageElement.m_Prefab == Entity.Null)
						{
							num9 += vehicleCarriageElement.m_Count.x;
							continue;
						}
						if (publicTransportPurpose != 0 && m_PublicTransportVehicleData.TryGetComponent(vehicleCarriageElement.m_Prefab, out var componentData))
						{
							passengerCapacity.y += componentData.m_PassengerCapacity * vehicleCarriageElement.m_Count.x;
						}
						if (cargoResources != Resource.NoResource && m_CargoTransportVehicleData.TryGetComponent(vehicleCarriageElement.m_Prefab, out var componentData2))
						{
							cargoCapacity.y += componentData2.m_CargoCapacity * vehicleCarriageElement.m_Count.x;
						}
					}
				}
			}
			if (!isMultipleUnitTrain)
			{
				passengerCapacity.y += passengerCapacity.x;
				cargoCapacity.y += cargoCapacity.x;
				num9--;
			}
			if (num9 > 0)
			{
				passengerCapacity.y += passengerCapacity.x * num9;
				cargoCapacity.y += cargoCapacity.x * num9;
			}
			passengerCapacity.x = passengerCapacity.y;
			cargoCapacity.x = cargoCapacity.y;
		}
		return entity;
	}
```

- `public ListVehicles(Game.Prefabs.TransportType transportType, Game.Vehicles.EnergyTypes energyTypes, Game.Vehicles.SizeClass sizeClass, Game.Prefabs.PublicTransportPurpose publicTransportPurpose, Game.Economy.Resource cargoResources, Unity.Collections.NativeList<Unity.Entities.Entity> primaryPrefabs, Unity.Collections.NativeList<Unity.Entities.Entity> secondaryPrefabs) : System.Void`  

```csharp
public void ListVehicles(TransportType transportType, EnergyTypes energyTypes, SizeClass sizeClass, PublicTransportPurpose publicTransportPurpose, Resource cargoResources, NativeList<Entity> primaryPrefabs, NativeList<Entity> secondaryPrefabs)
	{
		Random random = Random.CreateFromIndex(0u);
		int2 passengerCapacity = ((publicTransportPurpose != 0) ? new int2(1, int.MaxValue) : ((int2)0));
		int2 cargoCapacity = ((cargoResources != Resource.NoResource) ? new int2(1, int.MaxValue) : ((int2)0));
		GetRandomVehicle(ref random, transportType, energyTypes, sizeClass, publicTransportPurpose, cargoResources, Entity.Null, Entity.Null, primaryPrefabs, secondaryPrefabs, ignoreTheme: false, out var _, out var _, out var _, ref passengerCapacity, ref cargoCapacity);
	}
```

- `private PickVehicle(Unity.Mathematics.Random& random, System.Int32 probability, System.Int32 priority, System.Int32& totalProbability, System.Int32& selectedPriority) : System.Boolean`  

```csharp
private bool PickVehicle(ref Random random, int probability, int priority, ref int totalProbability, ref int selectedPriority)
	{
		if (priority < selectedPriority)
		{
			return false;
		}
		if (priority > selectedPriority)
		{
			totalProbability = 0;
			selectedPriority = priority;
		}
		totalProbability += probability;
		return random.NextInt(totalProbability) < probability;
	}
```

- `public PostUpdate(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public void PostUpdate(JobHandle jobHandle)
	{
		m_PrefabChunks.Dispose(jobHandle);
	}
```

- `public PreUpdate(Unity.Entities.SystemBase system, Game.City.CityConfigurationSystem cityConfigurationSystem, Unity.Entities.EntityQuery query, Unity.Collections.Allocator allocator, Unity.Jobs.JobHandle& jobHandle) : System.Void`  

```csharp
public void PreUpdate(SystemBase system, CityConfigurationSystem cityConfigurationSystem, EntityQuery query, Allocator allocator, out JobHandle jobHandle)
	{
		m_PrefabChunks = query.ToArchetypeChunkListAsync(allocator, out jobHandle);
		m_RequirementData.Update(system, cityConfigurationSystem);
		m_EntityType.Update(system);
		m_PublicTransportVehicleType.Update(system);
		m_CargoTransportVehicleType.Update(system);
		m_TrainType.Update(system);
		m_TrainEngineType.Update(system);
		m_TrainCarriageType.Update(system);
		m_MultipleUnitTrainType.Update(system);
		m_TaxiType.Update(system);
		m_CarType.Update(system);
		m_AircraftType.Update(system);
		m_AirplaneType.Update(system);
		m_HelicopterType.Update(system);
		m_WatercraftType.Update(system);
		m_ObjectData.Update(system);
		m_MovingObjectData.Update(system);
		m_TrainObjectData.Update(system);
		m_PublicTransportVehicleData.Update(system);
		m_CargoTransportVehicleData.Update(system);
		m_VehicleCarriages.Update(system);
	}
```

- `public SelectVehicle(Unity.Mathematics.Random& random, Game.Prefabs.TransportType transportType, Game.Vehicles.EnergyTypes energyTypes, Game.Vehicles.SizeClass sizeClass, Game.Prefabs.PublicTransportPurpose publicTransportPurpose, Game.Economy.Resource cargoResources, Unity.Entities.Entity& primaryPrefab, Unity.Entities.Entity& secondaryPrefab, Unity.Mathematics.int2& passengerCapacity, Unity.Mathematics.int2& cargoCapacity) : System.Void`  

```csharp
public void SelectVehicle(ref Random random, TransportType transportType, EnergyTypes energyTypes, SizeClass sizeClass, PublicTransportPurpose publicTransportPurpose, Resource cargoResources, out Entity primaryPrefab, out Entity secondaryPrefab, ref int2 passengerCapacity, ref int2 cargoCapacity)
	{
		primaryPrefab = GetRandomVehicle(ref random, transportType, energyTypes, sizeClass, publicTransportPurpose, cargoResources, Entity.Null, Entity.Null, default(NativeList<Entity>), default(NativeList<Entity>), ignoreTheme: false, out var _, out var _, out secondaryPrefab, ref passengerCapacity, ref cargoCapacity);
	}
```


