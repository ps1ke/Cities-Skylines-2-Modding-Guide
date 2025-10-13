# Game.Simulation.LandValueSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.LandValueCell>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LandValueSystem : Game.Simulation.CellMapSystem<Game.Simulation.LandValueCell>, Colossal.Serialization.Entities.IJobSerializable
{
    private Unity.Entities.EntityQuery m_EdgeGroup;
    private Unity.Entities.EntityQuery m_NodeGroup;
    private Unity.Entities.EntityQuery m_AttractivenessParameterQuery;
    private Unity.Entities.EntityQuery m_LandValueParameterQuery;
    private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
    private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
    private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
    private Game.Simulation.AvailabilityInfoToGridSystem m_AvailabilityInfoToGridSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Simulation.TerrainAttractivenessSystem m_TerrainAttractivenessSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem;
    private Game.Simulation.LandValueSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kTextureSize;
    public static readonly System.Int32 kUpdatesPerDay;

    public Unity.Mathematics.int2 TextureSize { get; }

    public LandValueSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
    public static System.Int32 GetCellIndex(Unity.Mathematics.float3 pos);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_EdgeGroup`  

```csharp
private Unity.Entities.EntityQuery m_EdgeGroup;
```

- `private Unity.Entities.EntityQuery m_NodeGroup`  

```csharp
private Unity.Entities.EntityQuery m_NodeGroup;
```

- `private Unity.Entities.EntityQuery m_AttractivenessParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_AttractivenessParameterQuery;
```

- `private Unity.Entities.EntityQuery m_LandValueParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_LandValueParameterQuery;
```

- `private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  

```csharp
private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
```

- `private Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  

```csharp
private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
```

- `private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem`  

```csharp
private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
```

- `private Game.Simulation.AvailabilityInfoToGridSystem m_AvailabilityInfoToGridSystem`  

```csharp
private Game.Simulation.AvailabilityInfoToGridSystem m_AvailabilityInfoToGridSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Simulation.TerrainAttractivenessSystem m_TerrainAttractivenessSystem`  

```csharp
private Game.Simulation.TerrainAttractivenessSystem m_TerrainAttractivenessSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem`  

```csharp
private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem;
```

- `private Game.Simulation.LandValueSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.LandValueSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kTextureSize`  

```csharp
public static readonly System.Int32 kTextureSize;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Properties

- `public Unity.Mathematics.int2 TextureSize { get }`  

```csharp
public Unity.Mathematics.int2 TextureSize { get; }
```


## Constructors

- `public LandValueSystem()`  

```csharp
[Preserve]
	public LandValueSystem()
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

- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  

```csharp
public static float3 GetCellCenter(int index)
	{
		return CellMapSystem<LandValueCell>.GetCellCenter(index, kTextureSize);
	}
```

- `public static GetCellIndex(Unity.Mathematics.float3 pos) : System.Int32`  

```csharp
public static int GetCellIndex(float3 pos)
	{
		int num = CellMapSystem<LandValueCell>.kMapSize / kTextureSize;
		return Mathf.FloorToInt(((float)(CellMapSystem<LandValueCell>.kMapSize / 2) + pos.x) / (float)num) + Mathf.FloorToInt(((float)(CellMapSystem<LandValueCell>.kMapSize / 2) + pos.z) / (float)num) * kTextureSize;
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 262144 / kUpdatesPerDay;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		Assert.IsTrue(kTextureSize == TerrainAttractivenessSystem.kTextureSize);
		CreateTextures(kTextureSize);
		m_NetSearchSystem = base.World.GetOrCreateSystemManaged<SearchSystem>();
		m_GroundPollutionSystem = base.World.GetOrCreateSystemManaged<GroundPollutionSystem>();
		m_AirPollutionSystem = base.World.GetOrCreateSystemManaged<AirPollutionSystem>();
		m_NoisePollutionSystem = base.World.GetOrCreateSystemManaged<NoisePollutionSystem>();
		m_TerrainAttractivenessSystem = base.World.GetOrCreateSystemManaged<TerrainAttractivenessSystem>();
		m_AvailabilityInfoToGridSystem = base.World.GetOrCreateSystemManaged<AvailabilityInfoToGridSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_TelecomCoverageSystem = base.World.GetOrCreateSystemManaged<TelecomCoverageSystem>();
		m_AttractivenessParameterQuery = GetEntityQuery(ComponentType.ReadOnly<AttractivenessParameterData>());
		m_LandValueParameterQuery = GetEntityQuery(ComponentType.ReadOnly<LandValueParameterData>());
		m_EdgeGroup = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Edge>(),
				ComponentType.ReadWrite<LandValue>(),
				ComponentType.ReadOnly<Curve>()
			},
			Any = new ComponentType[0],
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		RequireAnyForUpdate(m_EdgeGroup);
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
		if (!m_EdgeGroup.IsEmptyIgnoreFilter)
		{
			EdgeUpdateJob jobData = new EdgeUpdateJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_EdgeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Edge_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ServiceCoverageType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_ServiceCoverage_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_AvailabilityType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_ResourceAvailability_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_LandValues = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LandValue_RW_ComponentLookup, ref base.CheckedStateRef),
				m_LandValueParameterData = m_LandValueParameterQuery.GetSingleton<LandValueParameterData>()
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_EdgeGroup, base.Dependency);
		}
		JobHandle dependencies;
		JobHandle dependencies2;
		JobHandle dependencies3;
		JobHandle dependencies4;
		JobHandle dependencies5;
		JobHandle dependencies6;
		JobHandle dependencies7;
		JobHandle deps;
		LandValueMapUpdateJob jobData2 = new LandValueMapUpdateJob
		{
			m_NetSearchTree = m_NetSearchSystem.GetNetSearchTree(readOnly: true, out dependencies),
			m_AttractiveMap = m_TerrainAttractivenessSystem.GetMap(readOnly: true, out dependencies2),
			m_GroundPollutionMap = m_GroundPollutionSystem.GetMap(readOnly: true, out dependencies3),
			m_AirPollutionMap = m_AirPollutionSystem.GetMap(readOnly: true, out dependencies4),
			m_NoisePollutionMap = m_NoisePollutionSystem.GetMap(readOnly: true, out dependencies5),
			m_AvailabilityInfoMap = m_AvailabilityInfoToGridSystem.GetMap(readOnly: true, out dependencies6),
			m_TelecomCoverageMap = m_TelecomCoverageSystem.GetData(readOnly: true, out dependencies7),
			m_LandValueMap = m_Map,
			m_LandValueData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LandValue_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TerrainHeightData = m_TerrainSystem.GetHeightData(),
			m_WaterSurfaceData = m_WaterSystem.GetSurfaceData(out deps),
			m_EdgeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AttractivenessParameterData = m_AttractivenessParameterQuery.GetSingleton<AttractivenessParameterData>(),
			m_LandValueParameterData = m_LandValueParameterQuery.GetSingleton<LandValueParameterData>(),
			m_CellSize = (float)CellMapSystem<LandValueCell>.kMapSize / (float)kTextureSize
		};
		base.Dependency = IJobParallelForExtensions.Schedule(jobData2, kTextureSize * kTextureSize, kTextureSize, JobHandle.CombineDependencies(dependencies, dependencies2, JobHandle.CombineDependencies(m_WriteDependencies, m_ReadDependencies, JobHandle.CombineDependencies(base.Dependency, deps, JobHandle.CombineDependencies(dependencies3, dependencies5, JobHandle.CombineDependencies(dependencies6, dependencies4, dependencies7))))));
		AddWriter(base.Dependency);
		m_NetSearchSystem.AddNetSearchTreeReader(base.Dependency);
		m_WaterSystem.AddSurfaceReader(base.Dependency);
		m_TerrainAttractivenessSystem.AddReader(base.Dependency);
		m_GroundPollutionSystem.AddReader(base.Dependency);
		m_AirPollutionSystem.AddReader(base.Dependency);
		m_NoisePollutionSystem.AddReader(base.Dependency);
		m_AvailabilityInfoToGridSystem.AddReader(base.Dependency);
		m_TelecomCoverageSystem.AddReader(base.Dependency);
		m_TerrainSystem.AddCPUHeightReader(base.Dependency);
		base.Dependency = JobHandle.CombineDependencies(m_ReadDependencies, m_WriteDependencies, base.Dependency);
	}
```


## Nested types

- `Game.Simulation.LandValueSystem+NetIterator`  
- `Game.Simulation.LandValueSystem+LandValueMapUpdateJob`  
- `Game.Simulation.LandValueSystem+EdgeUpdateJob`  
- `Game.Simulation.LandValueSystem+TypeHandle`  

