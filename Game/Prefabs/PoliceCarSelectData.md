# Game.Prefabs.PoliceCarSelectData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct PoliceCarSelectData
{
    private Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_PrefabChunks;
    private Game.Prefabs.VehicleSelectRequirementData m_RequirementData;
    private Unity.Entities.EntityTypeHandle m_EntityType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.PoliceCarData> m_PoliceCarType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarData> m_CarType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.HelicopterData> m_HelicopterType;
    private Unity.Entities.ComponentLookup<Game.Prefabs.ObjectData> m_ObjectData;
    private Unity.Entities.ComponentLookup<Game.Prefabs.MovingObjectData> m_MovingObjectData;

    public PoliceCarSelectData(Unity.Entities.SystemBase system);

    public Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer commandBuffer, Unity.Mathematics.Random& random, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity prefab, Game.Prefabs.PolicePurpose& purposeMask, Game.Net.RoadTypes roadType, System.Boolean parked);
    public Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity prefab, Game.Prefabs.PolicePurpose& purposeMask, Game.Net.RoadTypes roadType, System.Boolean parked);
    private Unity.Entities.EntityArchetype GetArchetype(Unity.Entities.Entity prefab, System.Boolean parked);
    public static Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    private Unity.Entities.Entity GetRandomVehicle(Unity.Mathematics.Random& random, Game.Prefabs.PolicePurpose& purposeMask, Game.Net.RoadTypes roadType);
    private System.Boolean PickVehicle(Unity.Mathematics.Random& random, System.Int32 probability, System.Int32& totalProbability);
    public System.Void PostUpdate(Unity.Jobs.JobHandle jobHandle);
    public System.Void PreUpdate(Unity.Entities.SystemBase system, Game.City.CityConfigurationSystem cityConfigurationSystem, Unity.Entities.EntityQuery query, Unity.Collections.Allocator allocator, Unity.Jobs.JobHandle& jobHandle);
    public Unity.Entities.Entity SelectVehicle(Unity.Mathematics.Random& random, Game.Prefabs.PolicePurpose& purposeMask, Game.Net.RoadTypes roadType);
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

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.PoliceCarData> m_PoliceCarType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.PoliceCarData> m_PoliceCarType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarData> m_CarType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarData> m_CarType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.HelicopterData> m_HelicopterType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.HelicopterData> m_HelicopterType;
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

- `public PoliceCarSelectData(Unity.Entities.SystemBase system)`  

```csharp
public PoliceCarSelectData(SystemBase system)
	{
		m_PrefabChunks = default(NativeList<ArchetypeChunk>);
		m_RequirementData = new VehicleSelectRequirementData(system);
		m_EntityType = system.GetEntityTypeHandle();
		m_PoliceCarType = system.GetComponentTypeHandle<PoliceCarData>(isReadOnly: true);
		m_CarType = system.GetComponentTypeHandle<CarData>(isReadOnly: true);
		m_HelicopterType = system.GetComponentTypeHandle<HelicopterData>(isReadOnly: true);
		m_ObjectData = system.GetComponentLookup<ObjectData>(isReadOnly: true);
		m_MovingObjectData = system.GetComponentLookup<MovingObjectData>(isReadOnly: true);
	}
```


## Methods

- `public CreateVehicle(Unity.Entities.EntityCommandBuffer commandBuffer, Unity.Mathematics.Random& random, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity prefab, Game.Prefabs.PolicePurpose& purposeMask, Game.Net.RoadTypes roadType, System.Boolean parked) : Unity.Entities.Entity`  

```csharp
public Entity CreateVehicle(EntityCommandBuffer.ParallelWriter commandBuffer, int jobIndex, ref Random random, Transform transform, Entity source, Entity prefab, ref PolicePurpose purposeMask, RoadTypes roadType, bool parked)
	{
		if (prefab == Entity.Null)
		{
			prefab = GetRandomVehicle(ref random, ref purposeMask, roadType);
			if (prefab == Entity.Null)
			{
				return Entity.Null;
			}
		}
		Entity entity = commandBuffer.CreateEntity(jobIndex, GetArchetype(prefab, parked));
		commandBuffer.SetComponent(jobIndex, entity, transform);
		commandBuffer.SetComponent(jobIndex, entity, new PrefabRef(prefab));
		commandBuffer.SetComponent(jobIndex, entity, new PseudoRandomSeed(ref random));
		if (!parked)
		{
			commandBuffer.AddComponent(jobIndex, entity, new TripSource(source));
			commandBuffer.AddComponent(jobIndex, entity, default(Unspawned));
		}
		return entity;
	}
```

- `public CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity prefab, Game.Prefabs.PolicePurpose& purposeMask, Game.Net.RoadTypes roadType, System.Boolean parked) : Unity.Entities.Entity`  

```csharp
public Entity CreateVehicle(EntityCommandBuffer.ParallelWriter commandBuffer, int jobIndex, ref Random random, Transform transform, Entity source, Entity prefab, ref PolicePurpose purposeMask, RoadTypes roadType, bool parked)
	{
		if (prefab == Entity.Null)
		{
			prefab = GetRandomVehicle(ref random, ref purposeMask, roadType);
			if (prefab == Entity.Null)
			{
				return Entity.Null;
			}
		}
		Entity entity = commandBuffer.CreateEntity(jobIndex, GetArchetype(prefab, parked));
		commandBuffer.SetComponent(jobIndex, entity, transform);
		commandBuffer.SetComponent(jobIndex, entity, new PrefabRef(prefab));
		commandBuffer.SetComponent(jobIndex, entity, new PseudoRandomSeed(ref random));
		if (!parked)
		{
			commandBuffer.AddComponent(jobIndex, entity, new TripSource(source));
			commandBuffer.AddComponent(jobIndex, entity, default(Unspawned));
		}
		return entity;
	}
```

- `private GetArchetype(Unity.Entities.Entity prefab, System.Boolean parked) : Unity.Entities.EntityArchetype`  

```csharp
private EntityArchetype GetArchetype(Entity prefab, bool parked)
	{
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
			ComponentType.ReadOnly<PoliceCarData>(),
			ComponentType.ReadOnly<ObjectData>(),
			ComponentType.ReadOnly<PrefabData>()
		};
		entityQueryDesc.Any = new ComponentType[2]
		{
			ComponentType.ReadOnly<CarData>(),
			ComponentType.ReadOnly<HelicopterData>()
		};
		entityQueryDesc.None = new ComponentType[1] { ComponentType.ReadOnly<Locked>() };
		return entityQueryDesc;
	}
```

- `private GetRandomVehicle(Unity.Mathematics.Random& random, Game.Prefabs.PolicePurpose& purposeMask, Game.Net.RoadTypes roadType) : Unity.Entities.Entity`  

```csharp
private Entity GetRandomVehicle(ref Random random, ref PolicePurpose purposeMask, RoadTypes roadType)
	{
		Entity result = Entity.Null;
		PolicePurpose policePurpose = (PolicePurpose)0;
		int totalProbability = 0;
		for (int i = 0; i < m_PrefabChunks.Length; i++)
		{
			ArchetypeChunk chunk = m_PrefabChunks[i];
			if (roadType != RoadTypes.Car)
			{
				if (roadType != RoadTypes.Helicopter || !chunk.Has(ref m_HelicopterType))
				{
					continue;
				}
			}
			else if (!chunk.Has(ref m_CarType))
			{
				continue;
			}
			NativeArray<Entity> nativeArray = chunk.GetNativeArray(m_EntityType);
			NativeArray<PoliceCarData> nativeArray2 = chunk.GetNativeArray(ref m_PoliceCarType);
			VehicleSelectRequirementData.Chunk chunk2 = m_RequirementData.GetChunk(chunk);
			for (int j = 0; j < nativeArray2.Length; j++)
			{
				PoliceCarData policeCarData = nativeArray2[j];
				if ((policeCarData.m_PurposeMask & purposeMask) != 0 && m_RequirementData.CheckRequirements(ref chunk2, j) && PickVehicle(ref random, 100, ref totalProbability))
				{
					result = nativeArray[j];
					policePurpose = policeCarData.m_PurposeMask;
				}
			}
		}
		purposeMask = policePurpose;
		return result;
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
		m_PoliceCarType.Update(system);
		m_CarType.Update(system);
		m_HelicopterType.Update(system);
		m_ObjectData.Update(system);
		m_MovingObjectData.Update(system);
	}
```

- `public SelectVehicle(Unity.Mathematics.Random& random, Game.Prefabs.PolicePurpose& purposeMask, Game.Net.RoadTypes roadType) : Unity.Entities.Entity`  

```csharp
public Entity SelectVehicle(ref Random random, ref PolicePurpose purposeMask, RoadTypes roadType)
	{
		return GetRandomVehicle(ref random, ref purposeMask, roadType);
	}
```


