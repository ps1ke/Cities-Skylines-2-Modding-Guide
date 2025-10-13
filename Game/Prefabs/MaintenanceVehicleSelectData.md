# Game.Prefabs.MaintenanceVehicleSelectData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct MaintenanceVehicleSelectData
{
    private Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_PrefabChunks;
    private Game.Prefabs.VehicleSelectRequirementData m_RequirementData;
    private Unity.Entities.EntityTypeHandle m_EntityType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.MaintenanceVehicleData> m_MaintenanceVehicleType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.ObjectGeometryData> m_ObjectGeometryDataType;
    private Unity.Entities.ComponentLookup<Game.Prefabs.ObjectData> m_ObjectData;
    private Unity.Entities.ComponentLookup<Game.Prefabs.MovingObjectData> m_MovingObjectData;

    public MaintenanceVehicleSelectData(Unity.Entities.SystemBase system);

    public Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer commandBuffer, Unity.Mathematics.Random& random, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity prefab, Game.Simulation.MaintenanceType allMaintenanceTypes, Game.Simulation.MaintenanceType anyMaintenanceTypes, Unity.Mathematics.float4 maxParkingSizes, System.Boolean parked);
    public Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity prefab, Game.Simulation.MaintenanceType allMaintenanceTypes, Game.Simulation.MaintenanceType anyMaintenanceTypes, Unity.Mathematics.float4 maxParkingSizes, System.Boolean parked);
    private Unity.Entities.EntityArchetype GetArchetype(Unity.Entities.Entity prefab, System.Boolean parked);
    public static Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    private Unity.Entities.Entity GetRandomVehicle(Unity.Mathematics.Random& random, Game.Simulation.MaintenanceType allMaintenanceTypes, Game.Simulation.MaintenanceType anyMaintenanceTypes, Unity.Mathematics.float4 maxParkingSizes);
    private System.Boolean PickVehicle(Unity.Mathematics.Random& random, System.Int32 probability, System.Int32& totalProbability);
    public System.Void PostUpdate(Unity.Jobs.JobHandle jobHandle);
    public System.Void PreUpdate(Unity.Entities.SystemBase system, Game.City.CityConfigurationSystem cityConfigurationSystem, Unity.Entities.EntityQuery query, Unity.Collections.Allocator allocator, Unity.Jobs.JobHandle& jobHandle);
    public Unity.Entities.Entity SelectVehicle(Unity.Mathematics.Random& random, Game.Simulation.MaintenanceType allMaintenanceTypes, Game.Simulation.MaintenanceType anyMaintenanceTypes, Unity.Mathematics.float4 maxParkingSizes);
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

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.MaintenanceVehicleData> m_MaintenanceVehicleType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.MaintenanceVehicleData> m_MaintenanceVehicleType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.ObjectGeometryData> m_ObjectGeometryDataType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.ObjectGeometryData> m_ObjectGeometryDataType;
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

- `public MaintenanceVehicleSelectData(Unity.Entities.SystemBase system)`  

```csharp
public MaintenanceVehicleSelectData(SystemBase system)
	{
		m_PrefabChunks = default(NativeList<ArchetypeChunk>);
		m_RequirementData = new VehicleSelectRequirementData(system);
		m_EntityType = system.GetEntityTypeHandle();
		m_MaintenanceVehicleType = system.GetComponentTypeHandle<MaintenanceVehicleData>(isReadOnly: true);
		m_ObjectGeometryDataType = system.GetComponentTypeHandle<ObjectGeometryData>(isReadOnly: true);
		m_ObjectData = system.GetComponentLookup<ObjectData>(isReadOnly: true);
		m_MovingObjectData = system.GetComponentLookup<MovingObjectData>(isReadOnly: true);
	}
```


## Methods

- `public CreateVehicle(Unity.Entities.EntityCommandBuffer commandBuffer, Unity.Mathematics.Random& random, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity prefab, Game.Simulation.MaintenanceType allMaintenanceTypes, Game.Simulation.MaintenanceType anyMaintenanceTypes, Unity.Mathematics.float4 maxParkingSizes, System.Boolean parked) : Unity.Entities.Entity`  

```csharp
public Entity CreateVehicle(EntityCommandBuffer.ParallelWriter commandBuffer, int jobIndex, ref Random random, Transform transform, Entity source, Entity prefab, MaintenanceType allMaintenanceTypes, MaintenanceType anyMaintenanceTypes, float4 maxParkingSizes, bool parked)
	{
		if (prefab == Entity.Null)
		{
			prefab = GetRandomVehicle(ref random, allMaintenanceTypes, anyMaintenanceTypes, maxParkingSizes);
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

- `public CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity prefab, Game.Simulation.MaintenanceType allMaintenanceTypes, Game.Simulation.MaintenanceType anyMaintenanceTypes, Unity.Mathematics.float4 maxParkingSizes, System.Boolean parked) : Unity.Entities.Entity`  

```csharp
public Entity CreateVehicle(EntityCommandBuffer.ParallelWriter commandBuffer, int jobIndex, ref Random random, Transform transform, Entity source, Entity prefab, MaintenanceType allMaintenanceTypes, MaintenanceType anyMaintenanceTypes, float4 maxParkingSizes, bool parked)
	{
		if (prefab == Entity.Null)
		{
			prefab = GetRandomVehicle(ref random, allMaintenanceTypes, anyMaintenanceTypes, maxParkingSizes);
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
		entityQueryDesc.All = new ComponentType[4]
		{
			ComponentType.ReadOnly<MaintenanceVehicleData>(),
			ComponentType.ReadOnly<CarData>(),
			ComponentType.ReadOnly<ObjectData>(),
			ComponentType.ReadOnly<PrefabData>()
		};
		entityQueryDesc.None = new ComponentType[1] { ComponentType.ReadOnly<Locked>() };
		return entityQueryDesc;
	}
```

- `private GetRandomVehicle(Unity.Mathematics.Random& random, Game.Simulation.MaintenanceType allMaintenanceTypes, Game.Simulation.MaintenanceType anyMaintenanceTypes, Unity.Mathematics.float4 maxParkingSizes) : Unity.Entities.Entity`  

```csharp
private Entity GetRandomVehicle(ref Random random, MaintenanceType allMaintenanceTypes, MaintenanceType anyMaintenanceTypes, float4 maxParkingSizes)
	{
		Entity result = Entity.Null;
		int totalProbability = 0;
		int num = 100;
		for (int i = 0; i < m_PrefabChunks.Length; i++)
		{
			ArchetypeChunk chunk = m_PrefabChunks[i];
			NativeArray<Entity> nativeArray = chunk.GetNativeArray(m_EntityType);
			NativeArray<MaintenanceVehicleData> nativeArray2 = chunk.GetNativeArray(ref m_MaintenanceVehicleType);
			NativeArray<ObjectGeometryData> nativeArray3 = chunk.GetNativeArray(ref m_ObjectGeometryDataType);
			VehicleSelectRequirementData.Chunk chunk2 = m_RequirementData.GetChunk(chunk);
			for (int j = 0; j < nativeArray2.Length; j++)
			{
				MaintenanceVehicleData maintenanceVehicleData = nativeArray2[j];
				if ((maintenanceVehicleData.m_MaintenanceType & allMaintenanceTypes) != allMaintenanceTypes || ((maintenanceVehicleData.m_MaintenanceType & anyMaintenanceTypes) == 0 && anyMaintenanceTypes != MaintenanceType.None) || !m_RequirementData.CheckRequirements(ref chunk2, j))
				{
					continue;
				}
				float offset;
				bool4 @bool = VehicleUtils.GetParkingSize(nativeArray3[j], out offset).xyxy > maxParkingSizes;
				if (math.all(@bool | @bool.yxwz))
				{
					continue;
				}
				int num2 = math.select(math.countbits((int)(maintenanceVehicleData.m_MaintenanceType ^ allMaintenanceTypes)), 0, allMaintenanceTypes == MaintenanceType.None);
				if (num2 <= num)
				{
					if (num2 < num)
					{
						totalProbability = 0;
						num = num2;
					}
					if (PickVehicle(ref random, 100, ref totalProbability))
					{
						result = nativeArray[j];
					}
				}
			}
		}
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
		m_MaintenanceVehicleType.Update(system);
		m_ObjectGeometryDataType.Update(system);
		m_ObjectData.Update(system);
		m_MovingObjectData.Update(system);
	}
```

- `public SelectVehicle(Unity.Mathematics.Random& random, Game.Simulation.MaintenanceType allMaintenanceTypes, Game.Simulation.MaintenanceType anyMaintenanceTypes, Unity.Mathematics.float4 maxParkingSizes) : Unity.Entities.Entity`  

```csharp
public Entity SelectVehicle(ref Random random, MaintenanceType allMaintenanceTypes, MaintenanceType anyMaintenanceTypes, float4 maxParkingSizes)
	{
		return GetRandomVehicle(ref random, allMaintenanceTypes, anyMaintenanceTypes, maxParkingSizes);
	}
```


