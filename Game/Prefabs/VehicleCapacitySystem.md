# Game.Prefabs.VehicleCapacitySystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class VehicleCapacitySystem : Game.GameSystemBase, Game.Serialization.IPostDeserialize
{
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Unity.Entities.EntityQuery m_UpdatedQuery;
    private Unity.Entities.EntityQuery m_DeliveryTruckQuery;
    private Unity.Collections.NativeList<Game.Prefabs.DeliveryTruckSelectItem> m_DeliveryTruckItems;
    private Unity.Jobs.JobHandle m_WriteDependency;
    private Game.Prefabs.VehicleSelectRequirementData m_VehicleSelectRequirementData;
    private System.Boolean m_RequireUpdate;
    private Game.Prefabs.VehicleCapacitySystem+TypeHandle __TypeHandle;

    public VehicleCapacitySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public Game.Prefabs.DeliveryTruckSelectData GetDeliveryTruckSelectData();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Unity.Entities.EntityQuery m_UpdatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedQuery;
```

- `private Unity.Entities.EntityQuery m_DeliveryTruckQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeliveryTruckQuery;
```

- `private Unity.Collections.NativeList<Game.Prefabs.DeliveryTruckSelectItem> m_DeliveryTruckItems`  

```csharp
private Unity.Collections.NativeList<Game.Prefabs.DeliveryTruckSelectItem> m_DeliveryTruckItems;
```

- `private Unity.Jobs.JobHandle m_WriteDependency`  

```csharp
private Unity.Jobs.JobHandle m_WriteDependency;
```

- `private Game.Prefabs.VehicleSelectRequirementData m_VehicleSelectRequirementData`  

```csharp
private Game.Prefabs.VehicleSelectRequirementData m_VehicleSelectRequirementData;
```

- `private System.Boolean m_RequireUpdate`  

```csharp
private System.Boolean m_RequireUpdate;
```

- `private Game.Prefabs.VehicleCapacitySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.VehicleCapacitySystem+TypeHandle __TypeHandle;
```


## Constructors

- `public VehicleCapacitySystem()`  

```csharp
[Preserve]
	public VehicleCapacitySystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		new EntityQueryBuilder(Allocator.Temp).Dispose();
	}
```

- `public GetDeliveryTruckSelectData() : Game.Prefabs.DeliveryTruckSelectData`  

```csharp
public DeliveryTruckSelectData GetDeliveryTruckSelectData()
	{
		m_WriteDependency.Complete();
		return new DeliveryTruckSelectData(m_DeliveryTruckItems.AsArray());
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_VehicleSelectRequirementData = new VehicleSelectRequirementData(this);
		m_UpdatedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<VehicleData>(),
				ComponentType.ReadOnly<PrefabData>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_DeliveryTruckQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[4]
			{
				ComponentType.ReadOnly<DeliveryTruckData>(),
				ComponentType.ReadOnly<CarData>(),
				ComponentType.ReadOnly<ObjectData>(),
				ComponentType.ReadOnly<PrefabData>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Locked>() }
		});
		m_DeliveryTruckItems = new NativeList<DeliveryTruckSelectItem>(10, Allocator.Persistent);
	}
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected override void OnCreateForCompiler()
	{
		base.OnCreateForCompiler();
		__AssignQueries(ref base.CheckedStateRef);
		__TypeHandle.__AssignHandles(ref base.CheckedStateRef);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_DeliveryTruckItems.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_RequireUpdate || !m_UpdatedQuery.IsEmptyIgnoreFilter)
		{
			m_RequireUpdate = false;
			JobHandle outJobHandle;
			NativeList<ArchetypeChunk> prefabChunks = m_DeliveryTruckQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
			m_VehicleSelectRequirementData.Update(this, m_CityConfigurationSystem);
			JobHandle jobHandle = IJobExtensions.Schedule(new UpdateDeliveryTruckSelectJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_DeliveryTruckDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_DeliveryTruckData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CarTrailerDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_CarTrailerData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CarTractorDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_CarTractorData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabChunks = prefabChunks,
				m_RequirementData = m_VehicleSelectRequirementData,
				m_DeliveryTruckItems = m_DeliveryTruckItems
			}, JobHandle.CombineDependencies(base.Dependency, outJobHandle));
			prefabChunks.Dispose(jobHandle);
			m_WriteDependency = jobHandle;
			base.Dependency = jobHandle;
		}
	}
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PostDeserialize(Context context)
	{
		if (context.purpose == Purpose.NewGame || context.purpose == Purpose.LoadGame)
		{
			m_RequireUpdate = true;
		}
	}
```


## Nested types

- `Game.Prefabs.VehicleCapacitySystem+TypeHandle`  

