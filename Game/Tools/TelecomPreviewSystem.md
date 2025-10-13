# Game.Tools.TelecomPreviewSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.TelecomCoverage>`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TelecomPreviewSystem : Game.Simulation.CellMapSystem<Game.Simulation.TelecomCoverage>
{
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_DensityQuery;
    private Unity.Entities.EntityQuery m_FacilityQuery;
    private Unity.Entities.EntityQuery m_ModifiedQuery;
    private System.Boolean m_ForceUpdate;
    private Unity.Collections.NativeArray<Game.Simulation.TelecomStatus> m_Status;
    private Game.Tools.TelecomPreviewSystem+TypeHandle __TypeHandle;

    public Unity.Mathematics.int2 TextureSize { get; }

    public TelecomPreviewSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnStartRunning();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Entities.EntityQuery m_DensityQuery`  

```csharp
private Unity.Entities.EntityQuery m_DensityQuery;
```

- `private Unity.Entities.EntityQuery m_FacilityQuery`  

```csharp
private Unity.Entities.EntityQuery m_FacilityQuery;
```

- `private Unity.Entities.EntityQuery m_ModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_ModifiedQuery;
```

- `private System.Boolean m_ForceUpdate`  

```csharp
private System.Boolean m_ForceUpdate;
```

- `private Unity.Collections.NativeArray<Game.Simulation.TelecomStatus> m_Status`  

```csharp
private Unity.Collections.NativeArray<Game.Simulation.TelecomStatus> m_Status;
```

- `private Game.Tools.TelecomPreviewSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.TelecomPreviewSystem+TypeHandle __TypeHandle;
```


## Properties

- `public Unity.Mathematics.int2 TextureSize { get }`  

```csharp
public Unity.Mathematics.int2 TextureSize { get; }
```


## Constructors

- `public TelecomPreviewSystem()`  

```csharp
[Preserve]
	public TelecomPreviewSystem()
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

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_DensityQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<HouseholdCitizen>(),
				ComponentType.ReadOnly<Employee>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_FacilityQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Buildings.TelecomFacility>(), ComponentType.ReadOnly<Transform>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Game.Buildings.ServiceUpgrade>(), ComponentType.Exclude<Hidden>(), ComponentType.Exclude<Deleted>());
		m_ModifiedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Game.Buildings.TelecomFacility>(),
				ComponentType.ReadOnly<Transform>(),
				ComponentType.ReadOnly<PrefabRef>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_Status = new NativeArray<TelecomStatus>(0, Allocator.Persistent);
		CreateTextures(128);
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
		m_Status.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStartRunning()
	{
		base.OnStartRunning();
		m_ForceUpdate = true;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (!m_ModifiedQuery.IsEmptyIgnoreFilter || m_ForceUpdate)
		{
			m_ForceUpdate = false;
			JobHandle outJobHandle;
			NativeList<ArchetypeChunk> densityChunks = m_DensityQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
			JobHandle outJobHandle2;
			NativeList<ArchetypeChunk> facilityChunks = m_FacilityQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle2);
			JobHandle dependencies;
			JobHandle jobHandle = IJobExtensions.Schedule(new TelecomCoverageSystem.TelecomCoverageJob
			{
				m_DensityChunks = densityChunks,
				m_FacilityChunks = facilityChunks,
				m_TerrainHeightData = m_TerrainSystem.GetHeightData(),
				m_City = m_CitySystem.City,
				m_Preview = true,
				m_TelecomCoverage = GetMap(readOnly: false, out dependencies),
				m_TelecomStatus = m_Status,
				m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PropertyRenterType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TelecomFacilityType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_TelecomFacility_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_BuildingEfficiencyType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Efficiency_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_InstalledUpgradeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_HouseholdCitizenType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_EmployeeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Companies_Employee_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TelecomFacilityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_TelecomFacility_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingEfficiencyData = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Efficiency_RO_BufferLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabTelecomFacilityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TelecomFacilityData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CityModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef)
			}, JobHandle.CombineDependencies(job1: JobHandle.CombineDependencies(outJobHandle, outJobHandle2, dependencies), job0: base.Dependency));
			densityChunks.Dispose(jobHandle);
			facilityChunks.Dispose(jobHandle);
			m_TerrainSystem.AddCPUHeightReader(jobHandle);
			AddWriter(jobHandle);
			base.Dependency = jobHandle;
		}
	}
```


## Nested types

- `Game.Tools.TelecomPreviewSystem+TypeHandle`  

