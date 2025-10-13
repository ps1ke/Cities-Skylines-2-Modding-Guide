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
public TransportTrainCarriageSelectData(SystemBase system)
	{
		m_PrefabChunks = default(NativeList<ArchetypeChunk>);
		m_RequirementData = new VehicleSelectRequirementData(system);
		m_EntityType = system.GetEntityTypeHandle();
		m_CargoTransportVehicleType = system.GetComponentTypeHandle<CargoTransportVehicleData>(isReadOnly: true);
	}
```


## Methods

- `public static GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public static EntityQueryDesc GetEntityQueryDesc()
	{
		EntityQueryDesc entityQueryDesc = new EntityQueryDesc();
		entityQueryDesc.All = new ComponentType[3]
		{
			ComponentType.ReadOnly<CargoTransportVehicleData>(),
			ComponentType.ReadOnly<TrainCarriageData>(),
			ComponentType.ReadOnly<PrefabData>()
		};
		entityQueryDesc.None = new ComponentType[1] { ComponentType.ReadOnly<Locked>() };
		return entityQueryDesc;
	}
```

- `private PickVehicle(Unity.Mathematics.Random& random, System.Int32 probability, System.Int32& totalProbability) : System.Boolean`  

```csharp
private bool PickVehicle(ref Random random, int probability, ref int totalProbability)
	{
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
		m_CargoTransportVehicleType.Update(system);
	}
```

- `public SelectCarriagePrefab(Unity.Mathematics.Random& random, Game.Economy.Resource resource, System.Int32 amount) : Unity.Entities.Entity`  

```csharp
public Entity SelectCarriagePrefab(ref Random random, Resource resource, int amount)
	{
		Entity result = Entity.Null;
		int num = -amount;
		int totalProbability = 0;
		for (int i = 0; i < m_PrefabChunks.Length; i++)
		{
			ArchetypeChunk chunk = m_PrefabChunks[i];
			NativeArray<Entity> nativeArray = chunk.GetNativeArray(m_EntityType);
			NativeArray<CargoTransportVehicleData> nativeArray2 = chunk.GetNativeArray(ref m_CargoTransportVehicleType);
			VehicleSelectRequirementData.Chunk chunk2 = m_RequirementData.GetChunk(chunk);
			for (int j = 0; j < nativeArray2.Length; j++)
			{
				CargoTransportVehicleData cargoTransportVehicleData = nativeArray2[j];
				if ((cargoTransportVehicleData.m_Resources & resource) == Resource.NoResource || !m_RequirementData.CheckRequirements(ref chunk2, j))
				{
					continue;
				}
				int num2 = cargoTransportVehicleData.m_CargoCapacity - amount;
				if (num2 != num)
				{
					if ((num2 < 0 && num > num2) || (num >= 0 && num < num2))
					{
						continue;
					}
					num = num2;
					totalProbability = 0;
				}
				if (PickVehicle(ref random, 100, ref totalProbability))
				{
					result = nativeArray[j];
				}
			}
		}
		return result;
	}
```


