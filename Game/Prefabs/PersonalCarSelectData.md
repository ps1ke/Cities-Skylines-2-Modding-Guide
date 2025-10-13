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
public PersonalCarSelectData(SystemBase system)
	{
		m_PrefabChunks = default(NativeList<ArchetypeChunk>);
		m_RequirementData = new VehicleSelectRequirementData(system);
		m_EntityType = system.GetEntityTypeHandle();
		m_CarDataType = system.GetComponentTypeHandle<Game.Prefabs.CarData>(isReadOnly: true);
		m_PersonalCarDataType = system.GetComponentTypeHandle<PersonalCarData>(isReadOnly: true);
		m_CarTrailerDataType = system.GetComponentTypeHandle<CarTrailerData>(isReadOnly: true);
		m_CarTractorDataType = system.GetComponentTypeHandle<CarTractorData>(isReadOnly: true);
		m_ObjectDataType = system.GetComponentTypeHandle<ObjectData>(isReadOnly: true);
		m_MovingObjectDataType = system.GetComponentTypeHandle<MovingObjectData>(isReadOnly: true);
	}
```


## Methods

- `private CalculateProbability(System.Int32 passengerAmount, System.Int32 baggageAmount, Game.Prefabs.PersonalCarSelectData+CarData firstData, Game.Prefabs.PersonalCarSelectData+CarData secondData, System.Int32& probability, System.Int32& offset) : System.Void`  

```csharp
private void CalculateProbability(int passengerAmount, int baggageAmount, CarData firstData, CarData secondData, out int probability, out int offset)
	{
		int num = firstData.m_PersonalCarData.m_PassengerCapacity + secondData.m_PersonalCarData.m_PassengerCapacity;
		int num2 = firstData.m_PersonalCarData.m_BaggageCapacity + secondData.m_PersonalCarData.m_BaggageCapacity;
		int num3 = num - passengerAmount;
		int num4 = num2 - baggageAmount;
		offset = math.min(0, num3) + math.min(0, num4);
		offset = math.select(0, offset - 10, offset != 0) + math.min(0, 4 - num3) + math.min(0, 4 - num4);
		probability = firstData.m_PersonalCarData.m_Probability;
		probability = math.select(probability, probability * secondData.m_PersonalCarData.m_Probability / 50, secondData.m_Entity != Entity.Null);
		probability = math.max(1, probability / ((1 << math.max(0, num3)) + (1 << math.max(0, num4))));
	}
```

- `private CheckTractors(System.Int32 passengerAmount, System.Int32 baggageAmount, System.Int32 extraOffset, Game.Prefabs.PersonalCarSelectData+CarData secondData, System.Boolean noSlowVehicles, Unity.Mathematics.Random& random, Game.Prefabs.PersonalCarSelectData+CarData& bestFirst, Game.Prefabs.PersonalCarSelectData+CarData& bestSecond, System.Int32& totalProbability, System.Int32& bestOffset) : System.Void`  

```csharp
private void CheckTractors(int passengerAmount, int baggageAmount, int extraOffset, CarData secondData, bool noSlowVehicles, ref Random random, ref CarData bestFirst, ref CarData bestSecond, ref int totalProbability, ref int bestOffset)
	{
		for (int i = 0; i < m_PrefabChunks.Length; i++)
		{
			ArchetypeChunk chunk = m_PrefabChunks[i];
			NativeArray<CarTractorData> nativeArray = chunk.GetNativeArray(ref m_CarTractorDataType);
			if (nativeArray.Length == 0 || chunk.Has(ref m_CarTrailerDataType))
			{
				continue;
			}
			NativeArray<Entity> nativeArray2 = chunk.GetNativeArray(m_EntityType);
			NativeArray<Game.Prefabs.CarData> nativeArray3 = chunk.GetNativeArray(ref m_CarDataType);
			NativeArray<PersonalCarData> nativeArray4 = chunk.GetNativeArray(ref m_PersonalCarDataType);
			NativeArray<ObjectData> nativeArray5 = chunk.GetNativeArray(ref m_ObjectDataType);
			NativeArray<MovingObjectData> nativeArray6 = chunk.GetNativeArray(ref m_MovingObjectDataType);
			VehicleSelectRequirementData.Chunk chunk2 = m_RequirementData.GetChunk(chunk);
			for (int j = 0; j < nativeArray.Length; j++)
			{
				Game.Prefabs.CarData carData = nativeArray3[j];
				if ((noSlowVehicles && carData.m_MaxSpeed < 22.222223f) || !m_RequirementData.CheckRequirements(ref chunk2, j))
				{
					continue;
				}
				CarData carData2 = new CarData
				{
					m_PersonalCarData = nativeArray4[j],
					m_Entity = nativeArray2[j],
					m_TractorData = nativeArray[j]
				};
				if (carData2.m_TractorData.m_TrailerType == secondData.m_TrailerData.m_TrailerType && (!(carData2.m_TractorData.m_FixedTrailer != Entity.Null) || !(carData2.m_TractorData.m_FixedTrailer != secondData.m_Entity)) && (!(secondData.m_TrailerData.m_FixedTractor != Entity.Null) || !(secondData.m_TrailerData.m_FixedTractor != carData2.m_Entity)))
				{
					carData2.m_ObjectData = nativeArray5[j];
					carData2.m_MovingObjectData = nativeArray6[j];
					CalculateProbability(passengerAmount, baggageAmount, carData2, secondData, out var probability, out var offset);
					if (PickVehicle(ref random, probability, offset + extraOffset, ref totalProbability, ref bestOffset))
					{
						bestFirst = carData2;
						bestSecond = secondData;
					}
				}
			}
		}
	}
```

- `private CheckTrailers(System.Int32 passengerAmount, System.Int32 baggageAmount, System.Int32 extraOffset, Game.Prefabs.PersonalCarSelectData+CarData firstData, System.Boolean emptyOnly, System.Boolean noSlowVehicles, Unity.Mathematics.Random& random, Game.Prefabs.PersonalCarSelectData+CarData& bestFirst, Game.Prefabs.PersonalCarSelectData+CarData& bestSecond, System.Int32& totalProbability, System.Int32& bestOffset) : System.Void`  

```csharp
private void CheckTrailers(int passengerAmount, int baggageAmount, int extraOffset, CarData firstData, bool emptyOnly, bool noSlowVehicles, ref Random random, ref CarData bestFirst, ref CarData bestSecond, ref int totalProbability, ref int bestOffset)
	{
		for (int i = 0; i < m_PrefabChunks.Length; i++)
		{
			ArchetypeChunk chunk = m_PrefabChunks[i];
			NativeArray<CarTrailerData> nativeArray = chunk.GetNativeArray(ref m_CarTrailerDataType);
			if (nativeArray.Length == 0)
			{
				continue;
			}
			NativeArray<Entity> nativeArray2 = chunk.GetNativeArray(m_EntityType);
			NativeArray<Game.Prefabs.CarData> nativeArray3 = chunk.GetNativeArray(ref m_CarDataType);
			NativeArray<PersonalCarData> nativeArray4 = chunk.GetNativeArray(ref m_PersonalCarDataType);
			NativeArray<CarTractorData> nativeArray5 = chunk.GetNativeArray(ref m_CarTractorDataType);
			NativeArray<ObjectData> nativeArray6 = chunk.GetNativeArray(ref m_ObjectDataType);
			NativeArray<MovingObjectData> nativeArray7 = chunk.GetNativeArray(ref m_MovingObjectDataType);
			VehicleSelectRequirementData.Chunk chunk2 = m_RequirementData.GetChunk(chunk);
			for (int j = 0; j < nativeArray.Length; j++)
			{
				Game.Prefabs.CarData carData = nativeArray3[j];
				if ((noSlowVehicles && carData.m_MaxSpeed < 22.222223f) || !m_RequirementData.CheckRequirements(ref chunk2, j))
				{
					continue;
				}
				CarData carData2 = new CarData
				{
					m_PersonalCarData = nativeArray4[j]
				};
				if (emptyOnly && (carData2.m_PersonalCarData.m_PassengerCapacity != 0 || carData2.m_PersonalCarData.m_BaggageCapacity != 0))
				{
					continue;
				}
				carData2.m_Entity = nativeArray2[j];
				carData2.m_TrailerData = nativeArray[j];
				if (firstData.m_TractorData.m_TrailerType != carData2.m_TrailerData.m_TrailerType || (firstData.m_TractorData.m_FixedTrailer != Entity.Null && firstData.m_TractorData.m_FixedTrailer != carData2.m_Entity) || (carData2.m_TrailerData.m_FixedTractor != Entity.Null && carData2.m_TrailerData.m_FixedTractor != firstData.m_Entity))
				{
					continue;
				}
				carData2.m_ObjectData = nativeArray6[j];
				carData2.m_MovingObjectData = nativeArray7[j];
				if (nativeArray5.Length != 0)
				{
					carData2.m_TractorData = nativeArray5[j];
					if (carData2.m_TractorData.m_FixedTrailer != Entity.Null)
					{
						continue;
					}
				}
				CalculateProbability(passengerAmount, baggageAmount, firstData, carData2, out var probability, out var offset);
				if (PickVehicle(ref random, probability, offset + extraOffset, ref totalProbability, ref bestOffset))
				{
					bestFirst = firstData;
					bestSecond = carData2;
				}
			}
		}
	}
```

- `public CreateTrailer(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, System.Int32 passengerAmount, System.Int32 baggageAmount, System.Boolean noSlowVehicles, Unity.Entities.Entity tractorPrefab, Game.Objects.Transform tractorTransform, Game.Vehicles.PersonalCarFlags state, System.Boolean stopped, System.UInt32 delay = 0) : Unity.Entities.Entity`  

```csharp
public Entity CreateTrailer(EntityCommandBuffer.ParallelWriter commandBuffer, int jobIndex, ref Random random, int passengerAmount, int baggageAmount, bool noSlowVehicles, Entity tractorPrefab, Transform tractorTransform, PersonalCarFlags state, bool stopped, uint delay = 0u)
	{
		for (int i = 0; i < m_PrefabChunks.Length; i++)
		{
			ArchetypeChunk chunk = m_PrefabChunks[i];
			NativeArray<Entity> nativeArray = chunk.GetNativeArray(m_EntityType);
			NativeArray<PersonalCarData> nativeArray2 = chunk.GetNativeArray(ref m_PersonalCarDataType);
			NativeArray<CarTractorData> nativeArray3 = chunk.GetNativeArray(ref m_CarTractorDataType);
			VehicleSelectRequirementData.Chunk chunk2 = m_RequirementData.GetChunk(chunk);
			for (int j = 0; j < nativeArray3.Length; j++)
			{
				if (!(nativeArray[j] != tractorPrefab) && m_RequirementData.CheckRequirements(ref chunk2, j))
				{
					CarData firstData = new CarData
					{
						m_Entity = tractorPrefab,
						m_PersonalCarData = nativeArray2[j],
						m_TractorData = nativeArray3[j]
					};
					CarData bestFirst = default(CarData);
					CarData bestSecond = default(CarData);
					CalculateProbability(passengerAmount, baggageAmount, firstData, default(CarData), out var probability, out var offset);
					CheckTrailers(passengerAmount, baggageAmount, 0, firstData, emptyOnly: false, noSlowVehicles, ref random, ref bestFirst, ref bestSecond, ref probability, ref offset);
					if (bestSecond.m_Entity == Entity.Null)
					{
						return Entity.Null;
					}
					Transform transform = tractorTransform;
					transform.m_Position += math.rotate(tractorTransform.m_Rotation, firstData.m_TractorData.m_AttachPosition);
					transform.m_Position -= math.rotate(transform.m_Rotation, bestSecond.m_TrailerData.m_AttachPosition);
					return CreateVehicle(commandBuffer, jobIndex, ref random, bestSecond, transform, Entity.Null, Entity.Null, (PersonalCarFlags)0u, stopped, delay);
				}
			}
		}
		return Entity.Null;
	}
```

- `public CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, System.Int32 passengerAmount, System.Int32 baggageAmount, System.Boolean avoidTrailers, System.Boolean noSlowVehicles, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity keeper, Game.Vehicles.PersonalCarFlags state, System.Boolean stopped, System.UInt32 delay = 0) : Unity.Entities.Entity`  

```csharp
private Entity CreateVehicle(EntityCommandBuffer commandBuffer, ref Random random, CarData data, Transform transform, Entity source, Entity keeper, PersonalCarFlags state, bool stopped, uint delay)
	{
		Entity entity = ((!stopped) ? commandBuffer.CreateEntity(data.m_ObjectData.m_Archetype) : commandBuffer.CreateEntity(data.m_MovingObjectData.m_StoppedArchetype));
		commandBuffer.SetComponent(entity, transform);
		commandBuffer.SetComponent(entity, new Game.Vehicles.PersonalCar(keeper, state));
		commandBuffer.SetComponent(entity, new PrefabRef(data.m_Entity));
		commandBuffer.SetComponent(entity, new PseudoRandomSeed(ref random));
		if (source != Entity.Null)
		{
			commandBuffer.AddComponent(entity, new TripSource(source, delay));
			commandBuffer.AddComponent(entity, default(Unspawned));
		}
		return entity;
	}
```

- `public CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, System.Int32 passengerAmount, System.Int32 baggageAmount, System.Boolean avoidTrailers, System.Boolean noSlowVehicles, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity keeper, Game.Vehicles.PersonalCarFlags state, System.Boolean stopped, System.UInt32 delay, Unity.Entities.Entity& trailer, Unity.Entities.Entity& vehiclePrefab, Unity.Entities.Entity& trailerPrefab) : Unity.Entities.Entity`  

```csharp
private Entity CreateVehicle(EntityCommandBuffer commandBuffer, ref Random random, CarData data, Transform transform, Entity source, Entity keeper, PersonalCarFlags state, bool stopped, uint delay)
	{
		Entity entity = ((!stopped) ? commandBuffer.CreateEntity(data.m_ObjectData.m_Archetype) : commandBuffer.CreateEntity(data.m_MovingObjectData.m_StoppedArchetype));
		commandBuffer.SetComponent(entity, transform);
		commandBuffer.SetComponent(entity, new Game.Vehicles.PersonalCar(keeper, state));
		commandBuffer.SetComponent(entity, new PrefabRef(data.m_Entity));
		commandBuffer.SetComponent(entity, new PseudoRandomSeed(ref random));
		if (source != Entity.Null)
		{
			commandBuffer.AddComponent(entity, new TripSource(source, delay));
			commandBuffer.AddComponent(entity, default(Unspawned));
		}
		return entity;
	}
```

- `public CreateVehicle(Unity.Entities.EntityCommandBuffer commandBuffer, Unity.Mathematics.Random& random, System.Int32 passengerAmount, System.Int32 baggageAmount, System.Boolean avoidTrailers, System.Boolean noSlowVehicles, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity keeper, Game.Vehicles.PersonalCarFlags state, System.Boolean stopped, System.UInt32 delay = 0) : Unity.Entities.Entity`  

```csharp
private Entity CreateVehicle(EntityCommandBuffer commandBuffer, ref Random random, CarData data, Transform transform, Entity source, Entity keeper, PersonalCarFlags state, bool stopped, uint delay)
	{
		Entity entity = ((!stopped) ? commandBuffer.CreateEntity(data.m_ObjectData.m_Archetype) : commandBuffer.CreateEntity(data.m_MovingObjectData.m_StoppedArchetype));
		commandBuffer.SetComponent(entity, transform);
		commandBuffer.SetComponent(entity, new Game.Vehicles.PersonalCar(keeper, state));
		commandBuffer.SetComponent(entity, new PrefabRef(data.m_Entity));
		commandBuffer.SetComponent(entity, new PseudoRandomSeed(ref random));
		if (source != Entity.Null)
		{
			commandBuffer.AddComponent(entity, new TripSource(source, delay));
			commandBuffer.AddComponent(entity, default(Unspawned));
		}
		return entity;
	}
```

- `private CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Prefabs.PersonalCarSelectData+CarData data, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity keeper, Game.Vehicles.PersonalCarFlags state, System.Boolean stopped, System.UInt32 delay) : Unity.Entities.Entity`  

```csharp
private Entity CreateVehicle(EntityCommandBuffer commandBuffer, ref Random random, CarData data, Transform transform, Entity source, Entity keeper, PersonalCarFlags state, bool stopped, uint delay)
	{
		Entity entity = ((!stopped) ? commandBuffer.CreateEntity(data.m_ObjectData.m_Archetype) : commandBuffer.CreateEntity(data.m_MovingObjectData.m_StoppedArchetype));
		commandBuffer.SetComponent(entity, transform);
		commandBuffer.SetComponent(entity, new Game.Vehicles.PersonalCar(keeper, state));
		commandBuffer.SetComponent(entity, new PrefabRef(data.m_Entity));
		commandBuffer.SetComponent(entity, new PseudoRandomSeed(ref random));
		if (source != Entity.Null)
		{
			commandBuffer.AddComponent(entity, new TripSource(source, delay));
			commandBuffer.AddComponent(entity, default(Unspawned));
		}
		return entity;
	}
```

- `private CreateVehicle(Unity.Entities.EntityCommandBuffer commandBuffer, Unity.Mathematics.Random& random, Game.Prefabs.PersonalCarSelectData+CarData data, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity keeper, Game.Vehicles.PersonalCarFlags state, System.Boolean stopped, System.UInt32 delay) : Unity.Entities.Entity`  

```csharp
private Entity CreateVehicle(EntityCommandBuffer commandBuffer, ref Random random, CarData data, Transform transform, Entity source, Entity keeper, PersonalCarFlags state, bool stopped, uint delay)
	{
		Entity entity = ((!stopped) ? commandBuffer.CreateEntity(data.m_ObjectData.m_Archetype) : commandBuffer.CreateEntity(data.m_MovingObjectData.m_StoppedArchetype));
		commandBuffer.SetComponent(entity, transform);
		commandBuffer.SetComponent(entity, new Game.Vehicles.PersonalCar(keeper, state));
		commandBuffer.SetComponent(entity, new PrefabRef(data.m_Entity));
		commandBuffer.SetComponent(entity, new PseudoRandomSeed(ref random));
		if (source != Entity.Null)
		{
			commandBuffer.AddComponent(entity, new TripSource(source, delay));
			commandBuffer.AddComponent(entity, default(Unspawned));
		}
		return entity;
	}
```

- `public static GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public static EntityQueryDesc GetEntityQueryDesc()
	{
		EntityQueryDesc entityQueryDesc = new EntityQueryDesc();
		entityQueryDesc.All = new ComponentType[4]
		{
			ComponentType.ReadOnly<PersonalCarData>(),
			ComponentType.ReadOnly<Game.Prefabs.CarData>(),
			ComponentType.ReadOnly<MovingObjectData>(),
			ComponentType.ReadOnly<PrefabData>()
		};
		entityQueryDesc.None = new ComponentType[1] { ComponentType.ReadOnly<Locked>() };
		return entityQueryDesc;
	}
```

- `private GetVehicleData(Unity.Mathematics.Random& random, System.Int32 passengerAmount, System.Int32 baggageAmount, System.Boolean avoidTrailers, System.Boolean noSlowVehicles, Game.Prefabs.PersonalCarSelectData+CarData& bestFirst, Game.Prefabs.PersonalCarSelectData+CarData& bestSecond) : System.Boolean`  

```csharp
private bool GetVehicleData(ref Random random, int passengerAmount, int baggageAmount, bool avoidTrailers, bool noSlowVehicles, out CarData bestFirst, out CarData bestSecond)
	{
		bestFirst = default(CarData);
		bestSecond = default(CarData);
		int totalProbability = 0;
		int bestOffset = -11 - (passengerAmount + baggageAmount);
		for (int i = 0; i < m_PrefabChunks.Length; i++)
		{
			ArchetypeChunk chunk = m_PrefabChunks[i];
			NativeArray<Entity> nativeArray = chunk.GetNativeArray(m_EntityType);
			NativeArray<Game.Prefabs.CarData> nativeArray2 = chunk.GetNativeArray(ref m_CarDataType);
			NativeArray<PersonalCarData> nativeArray3 = chunk.GetNativeArray(ref m_PersonalCarDataType);
			NativeArray<CarTrailerData> nativeArray4 = chunk.GetNativeArray(ref m_CarTrailerDataType);
			NativeArray<CarTractorData> nativeArray5 = chunk.GetNativeArray(ref m_CarTractorDataType);
			NativeArray<ObjectData> nativeArray6 = chunk.GetNativeArray(ref m_ObjectDataType);
			NativeArray<MovingObjectData> nativeArray7 = chunk.GetNativeArray(ref m_MovingObjectDataType);
			VehicleSelectRequirementData.Chunk chunk2 = m_RequirementData.GetChunk(chunk);
			for (int j = 0; j < nativeArray3.Length; j++)
			{
				Game.Prefabs.CarData carData = nativeArray2[j];
				if ((noSlowVehicles && carData.m_MaxSpeed < 22.222223f) || !m_RequirementData.CheckRequirements(ref chunk2, j))
				{
					continue;
				}
				CarData carData2 = new CarData
				{
					m_PersonalCarData = nativeArray3[j]
				};
				if (carData2.m_PersonalCarData.m_PassengerCapacity == 0 && carData2.m_PersonalCarData.m_BaggageCapacity == 0)
				{
					continue;
				}
				carData2.m_Entity = nativeArray[j];
				carData2.m_ObjectData = nativeArray6[j];
				carData2.m_MovingObjectData = nativeArray7[j];
				bool flag = false;
				if (nativeArray4.Length != 0)
				{
					carData2.m_TrailerData = nativeArray4[j];
					flag = true;
				}
				if (nativeArray5.Length != 0)
				{
					carData2.m_TractorData = nativeArray5[j];
					if (carData2.m_TractorData.m_FixedTrailer != Entity.Null)
					{
						if (!flag)
						{
							int extraOffset = math.select(0, -1, avoidTrailers);
							CheckTrailers(passengerAmount, baggageAmount, extraOffset, carData2, emptyOnly: true, noSlowVehicles, ref random, ref bestFirst, ref bestSecond, ref totalProbability, ref bestOffset);
						}
						continue;
					}
				}
				if (flag)
				{
					int extraOffset2 = math.select(0, -1, avoidTrailers);
					CheckTractors(passengerAmount, baggageAmount, extraOffset2, carData2, noSlowVehicles, ref random, ref bestFirst, ref bestSecond, ref totalProbability, ref bestOffset);
					continue;
				}
				CalculateProbability(passengerAmount, baggageAmount, carData2, default(CarData), out var probability, out var offset);
				if (PickVehicle(ref random, probability, offset, ref totalProbability, ref bestOffset))
				{
					bestFirst = carData2;
					bestSecond = default(CarData);
				}
			}
		}
		return bestFirst.m_Entity != Entity.Null;
	}
```

- `private PickVehicle(Unity.Mathematics.Random& random, System.Int32 probability, System.Int32 offset, System.Int32& totalProbability, System.Int32& bestOffset) : System.Boolean`  

```csharp
private bool PickVehicle(ref Random random, int probability, int offset, ref int totalProbability, ref int bestOffset)
	{
		if (offset == bestOffset)
		{
			totalProbability += probability;
			return random.NextInt(totalProbability) < probability;
		}
		if (offset > bestOffset)
		{
			totalProbability = probability;
			bestOffset = offset;
			return true;
		}
		return false;
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
		m_CarDataType.Update(system);
		m_PersonalCarDataType.Update(system);
		m_CarTrailerDataType.Update(system);
		m_CarTractorDataType.Update(system);
		m_ObjectDataType.Update(system);
		m_MovingObjectDataType.Update(system);
	}
```


## Nested types

- `Game.Prefabs.PersonalCarSelectData+CarData`  

