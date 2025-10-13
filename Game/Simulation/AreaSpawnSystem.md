# Game.Simulation.AreaSpawnSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AreaSpawnSystem : Game.GameSystemBase
{
    private System.Boolean <debugFastSpawn>k__BackingField;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_AreaQuery;
    private Unity.Entities.EntityArchetype m_DefinitionArchetype;
    private Game.Simulation.AreaSpawnSystem+TypeHandle __TypeHandle;

    public System.Boolean debugFastSpawn { get; set; }

    public AreaSpawnSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private System.Boolean <debugFastSpawn>k__BackingField`  

```csharp
private System.Boolean <debugFastSpawn>k__BackingField;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_AreaQuery`  

```csharp
private Unity.Entities.EntityQuery m_AreaQuery;
```

- `private Unity.Entities.EntityArchetype m_DefinitionArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_DefinitionArchetype;
```

- `private Game.Simulation.AreaSpawnSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.AreaSpawnSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.Boolean debugFastSpawn { get; set }`  

```csharp
public System.Boolean debugFastSpawn { get; set; }
```


## Constructors

- `public AreaSpawnSystem()`  

```csharp
[Preserve]
	public AreaSpawnSystem()
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

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 64;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_AreaQuery = GetEntityQuery(ComponentType.ReadOnly<Area>(), ComponentType.ReadOnly<Geometry>(), ComponentType.ReadOnly<Game.Objects.SubObject>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Destroyed>(), ComponentType.Exclude<Deleted>());
		m_DefinitionArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<CreationDefinition>(), ComponentType.ReadWrite<ObjectDefinition>(), ComponentType.ReadWrite<Updated>(), ComponentType.ReadWrite<Deleted>());
		RequireForUpdate(m_AreaQuery);
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		JobHandle deps;
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new AreaSpawnJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_AreaType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_Area_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_GeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_Geometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_StorageType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_Storage_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ExtractorType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_Extractor_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NodeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_Node_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_TriangleType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_Triangle_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_SubObjectType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AttachmentData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Attachment_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SecondaryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Secondary_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CompanyData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_CompanyData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabStorageAreaData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_StorageAreaData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabExtractorAreaData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ExtractorAreaData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabAreaGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AreaGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabSpawnableObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabPlaceableObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PlaceableObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabNetGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SubAreas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_SubArea_RO_BufferLookup, ref base.CheckedStateRef),
			m_BuildingRenters = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabSubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabSubNets = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubNet_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabSubAreas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubArea_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabSubAreaNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubAreaNode_RO_BufferLookup, ref base.CheckedStateRef),
			m_PlaceholderObjectElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_PlaceholderObjectElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_ObjectRequirements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ObjectRequirementElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_DebugFastSpawn = debugFastSpawn,
			m_LefthandTraffic = m_CityConfigurationSystem.leftHandTraffic,
			m_RandomSeed = RandomSeed.Next(),
			m_DefinitionArchetype = m_DefinitionArchetype,
			m_TerrainHeightData = m_TerrainSystem.GetHeightData(),
			m_WaterSurfaceData = m_WaterSystem.GetSurfaceData(out deps),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		}, m_AreaQuery, JobHandle.CombineDependencies(base.Dependency, deps));
		m_TerrainSystem.AddCPUHeightReader(jobHandle);
		m_WaterSystem.AddSurfaceReader(jobHandle);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Simulation.AreaSpawnSystem+AreaSpawnJob`  
- `Game.Simulation.AreaSpawnSystem+TypeHandle`  

