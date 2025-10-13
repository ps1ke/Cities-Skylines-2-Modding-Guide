# Game.Simulation.ExtractorAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ExtractorAISystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityQuery m_ExtractorParameterQuery;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Unity.Mathematics.Random m_RandomSeed;
    private Unity.Entities.EntityQuery m_CompanyQuery;
    private Game.Simulation.ExtractorAISystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;
    public static readonly System.Int32 kMinimumEmployee;

    public ExtractorAISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Single GetArea(Unity.Entities.Entity mainBuilding, Unity.Entities.BufferLookup`1[[Game.Areas.SubArea, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subAreas, Unity.Entities.BufferLookup`1[[Game.Buildings.InstalledUpgrade, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& installedUpgrades, Unity.Entities.ComponentLookup`1[[Game.Areas.Lot, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& lots, Unity.Entities.ComponentLookup`1[[Game.Areas.Geometry, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& geometries);
    private static System.Single GetArea(Unity.Entities.DynamicBuffer<Game.Areas.SubArea> subAreas, Unity.Entities.ComponentLookup`1[[Game.Areas.Lot, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& lots, Unity.Entities.ComponentLookup`1[[Game.Areas.Geometry, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& geometries);
    public static System.Single GetResourcesInArea(Unity.Entities.Entity mainBuilding, Unity.Entities.BufferLookup`1[[Game.Areas.SubArea, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subAreas, Unity.Entities.BufferLookup`1[[Game.Buildings.InstalledUpgrade, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& installedUpgrades, Unity.Entities.ComponentLookup`1[[Game.Areas.Extractor, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& extractors);
    private static System.Single GetResourcesInArea(Unity.Entities.DynamicBuffer<Game.Areas.SubArea> subAreas, Unity.Entities.ComponentLookup`1[[Game.Areas.Extractor, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& extractors);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnStopRunning();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.EntityQuery m_ExtractorParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_ExtractorParameterQuery;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Unity.Mathematics.Random m_RandomSeed`  

```csharp
private Unity.Mathematics.Random m_RandomSeed;
```

- `private Unity.Entities.EntityQuery m_CompanyQuery`  

```csharp
private Unity.Entities.EntityQuery m_CompanyQuery;
```

- `private Game.Simulation.ExtractorAISystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ExtractorAISystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```

- `public static readonly System.Int32 kMinimumEmployee`  

```csharp
public static readonly System.Int32 kMinimumEmployee;
```


## Constructors

- `public ExtractorAISystem()`  

```csharp
[Preserve]
	public ExtractorAISystem()
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

- `public static GetArea(Unity.Entities.Entity mainBuilding, Unity.Entities.BufferLookup`1[[Game.Areas.SubArea, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subAreas, Unity.Entities.BufferLookup`1[[Game.Buildings.InstalledUpgrade, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& installedUpgrades, Unity.Entities.ComponentLookup`1[[Game.Areas.Lot, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& lots, Unity.Entities.ComponentLookup`1[[Game.Areas.Geometry, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& geometries) : System.Single`  

```csharp
private static float GetArea(DynamicBuffer<Game.Areas.SubArea> subAreas, ref ComponentLookup<Game.Areas.Lot> lots, ref ComponentLookup<Geometry> geometries)
	{
		float num = 0f;
		for (int i = 0; i < subAreas.Length; i++)
		{
			Entity area = subAreas[i].m_Area;
			if (lots.HasComponent(area))
			{
				num += geometries[area].m_SurfaceArea / 64f;
			}
		}
		return num;
	}
```

- `private static GetArea(Unity.Entities.DynamicBuffer<Game.Areas.SubArea> subAreas, Unity.Entities.ComponentLookup`1[[Game.Areas.Lot, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& lots, Unity.Entities.ComponentLookup`1[[Game.Areas.Geometry, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& geometries) : System.Single`  

```csharp
private static float GetArea(DynamicBuffer<Game.Areas.SubArea> subAreas, ref ComponentLookup<Game.Areas.Lot> lots, ref ComponentLookup<Geometry> geometries)
	{
		float num = 0f;
		for (int i = 0; i < subAreas.Length; i++)
		{
			Entity area = subAreas[i].m_Area;
			if (lots.HasComponent(area))
			{
				num += geometries[area].m_SurfaceArea / 64f;
			}
		}
		return num;
	}
```

- `public static GetResourcesInArea(Unity.Entities.Entity mainBuilding, Unity.Entities.BufferLookup`1[[Game.Areas.SubArea, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subAreas, Unity.Entities.BufferLookup`1[[Game.Buildings.InstalledUpgrade, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& installedUpgrades, Unity.Entities.ComponentLookup`1[[Game.Areas.Extractor, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& extractors) : System.Single`  

```csharp
private static float GetResourcesInArea(DynamicBuffer<Game.Areas.SubArea> subAreas, ref ComponentLookup<Extractor> extractors)
	{
		float num = 0f;
		for (int i = 0; i < subAreas.Length; i++)
		{
			Entity area = subAreas[i].m_Area;
			if (extractors.HasComponent(area))
			{
				Extractor extractor = extractors[area];
				num += math.max(0f, extractor.m_ResourceAmount - extractor.m_ExtractedAmount);
			}
		}
		return num;
	}
```

- `private static GetResourcesInArea(Unity.Entities.DynamicBuffer<Game.Areas.SubArea> subAreas, Unity.Entities.ComponentLookup`1[[Game.Areas.Extractor, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& extractors) : System.Single`  

```csharp
private static float GetResourcesInArea(DynamicBuffer<Game.Areas.SubArea> subAreas, ref ComponentLookup<Extractor> extractors)
	{
		float num = 0f;
		for (int i = 0; i < subAreas.Length; i++)
		{
			Entity area = subAreas[i].m_Area;
			if (extractors.HasComponent(area))
			{
				Extractor extractor = extractors[area];
				num += math.max(0f, extractor.m_ResourceAmount - extractor.m_ExtractedAmount);
			}
		}
		return num;
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 262144 / (kUpdatesPerDay * 16);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_RandomSeed = new Random(346745637u);
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		m_EconomyParameterQuery = GetEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
		m_ExtractorParameterQuery = GetEntityQuery(ComponentType.ReadOnly<ExtractorParameterData>());
		m_CompanyQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Companies.ProcessingCompany>(), ComponentType.ReadOnly<Game.Companies.ExtractorCompany>(), ComponentType.ReadWrite<WorkProvider>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<Resources>(), ComponentType.Exclude<ServiceAvailable>(), ComponentType.Exclude<Created>());
		RequireForUpdate(m_CompanyQuery);
		RequireForUpdate(m_EconomyParameterQuery);
		RequireForUpdate(m_ExtractorParameterQuery);
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

- `protected virtual OnStopRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStopRunning()
	{
		base.OnStopRunning();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		uint updateFrame = SimulationUtils.GetUpdateFrame(m_SimulationSystem.frameIndex, kUpdatesPerDay, 16);
		ExtractorAITickJob jobData = new ExtractorAITickJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_ResourceType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Economy_Resources_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_WorkProviderType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Companies_WorkProvider_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EmployeeBufType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Companies_Employee_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_IndustrialProcessDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_IndustrialProcessData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PropertyRenters = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PropertySeekers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Agents_PropertySeeker_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Attached = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Attached_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SubAreas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_SubArea_RO_BufferLookup, ref base.CheckedStateRef),
			m_InstalledUpgrades = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferLookup, ref base.CheckedStateRef),
			m_Lots = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Lot_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Geometries = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Geometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StorageLimitDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_StorageLimitData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_UpdateFrameIndex = updateFrame,
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_CompanyQuery, base.Dependency);
		m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
		m_ResourceSystem.AddPrefabsReader(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.ExtractorAISystem+ExtractorAITickJob`  
- `Game.Simulation.ExtractorAISystem+TypeHandle`  

