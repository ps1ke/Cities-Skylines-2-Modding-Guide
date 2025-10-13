# Game.Simulation.AttractionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AttractionSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.TerrainAttractivenessSystem m_TerrainAttractivenessSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Unity.Entities.EntityQuery m_BuildingGroup;
    private Unity.Entities.EntityQuery m_SettingsQuery;
    private Game.Simulation.AttractionSystem+TypeHandle __TypeHandle;

    public AttractionSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public static System.Void SetFactor(Unity.Collections.NativeArray<System.Int32> factors, Game.Simulation.AttractionSystem+AttractivenessFactor factor, System.Single attractiveness);
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.TerrainAttractivenessSystem m_TerrainAttractivenessSystem`  

```csharp
private Game.Simulation.TerrainAttractivenessSystem m_TerrainAttractivenessSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Unity.Entities.EntityQuery m_BuildingGroup`  

```csharp
private Unity.Entities.EntityQuery m_BuildingGroup;
```

- `private Unity.Entities.EntityQuery m_SettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_SettingsQuery;
```

- `private Game.Simulation.AttractionSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.AttractionSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AttractionSystem()`  

```csharp
[Preserve]
	public AttractionSystem()
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
		return 16;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_TerrainAttractivenessSystem = base.World.GetOrCreateSystemManaged<TerrainAttractivenessSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_SettingsQuery = GetEntityQuery(ComponentType.ReadOnly<AttractivenessParameterData>());
		m_BuildingGroup = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadWrite<AttractivenessProvider>(),
				ComponentType.ReadOnly<PrefabRef>(),
				ComponentType.ReadOnly<UpdateFrame>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Destroyed>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
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
		uint updateFrameWithInterval = SimulationUtils.GetUpdateFrameWithInterval(m_SimulationSystem.frameIndex, (uint)GetUpdateInterval(SystemUpdatePhase.GameSimulation), 16);
		JobHandle dependencies;
		AttractivenessJob jobData = new AttractivenessJob
		{
			m_AttractivenessType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_AttractivenessProvider_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EfficiencyType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Efficiency_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_SignatureType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Signature_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ParkType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Park_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InstalledUpgradeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_AttractionDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AttractionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ParkData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TerrainMap = m_TerrainAttractivenessSystem.GetData(readOnly: true, out dependencies),
			m_HeightData = m_TerrainSystem.GetHeightData(),
			m_Parameters = m_SettingsQuery.GetSingleton<AttractivenessParameterData>(),
			m_UpdateFrameIndex = updateFrameWithInterval
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_BuildingGroup, JobHandle.CombineDependencies(base.Dependency, dependencies));
		m_TerrainSystem.AddCPUHeightReader(base.Dependency);
		m_TerrainAttractivenessSystem.AddReader(base.Dependency);
	}
```

- `public static SetFactor(Unity.Collections.NativeArray<System.Int32> factors, Game.Simulation.AttractionSystem+AttractivenessFactor factor, System.Single attractiveness) : System.Void`  

```csharp
public static void SetFactor(NativeArray<int> factors, AttractivenessFactor factor, float attractiveness)
	{
		if (factors.IsCreated && factors.Length == 5)
		{
			factors[(int)factor] = Mathf.RoundToInt(attractiveness);
		}
	}
```


## Nested types

- `Game.Simulation.AttractionSystem+AttractivenessFactor`  
- `Game.Simulation.AttractionSystem+AttractivenessJob`  
- `Game.Simulation.AttractionSystem+TypeHandle`  

