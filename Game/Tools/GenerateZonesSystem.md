# Game.Tools.GenerateZonesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GenerateZonesSystem : Game.GameSystemBase
{
    private Game.Zones.SearchSystem m_ZoneSearchSystem;
    private Game.Common.ModificationBarrier1 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_DefinitionQuery;
    private Game.Tools.GenerateZonesSystem+TypeHandle __TypeHandle;

    public GenerateZonesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Zones.SearchSystem m_ZoneSearchSystem`  

```csharp
private Game.Zones.SearchSystem m_ZoneSearchSystem;
```

- `private Game.Common.ModificationBarrier1 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier1 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_DefinitionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionQuery;
```

- `private Game.Tools.GenerateZonesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.GenerateZonesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public GenerateZonesSystem()`  

```csharp
[Preserve]
	public GenerateZonesSystem()
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
		m_ZoneSearchSystem = base.World.GetOrCreateSystemManaged<SearchSystem>();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier1>();
		m_DefinitionQuery = GetEntityQuery(ComponentType.ReadOnly<CreationDefinition>(), ComponentType.ReadOnly<Zoning>(), ComponentType.ReadOnly<Updated>());
		RequireForUpdate(m_DefinitionQuery);
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
		NativeParallelMultiHashMap<Entity, CellData> zonedCells = new NativeParallelMultiHashMap<Entity, CellData>(1000, Allocator.TempJob);
		NativeList<Entity> nativeList = new NativeList<Entity>(20, Allocator.TempJob);
		JobHandle dependencies;
		FillBlocksListJob jobData = new FillBlocksListJob
		{
			m_CreationDefinitionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_CreationDefinition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ZoningType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Zoning_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BlockData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Zones_Block_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ZoneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ZoneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Cells = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Zones_Cell_RO_BufferLookup, ref base.CheckedStateRef),
			m_SearchTree = m_ZoneSearchSystem.GetSearchTree(readOnly: true, out dependencies),
			m_ZonedCells = zonedCells,
			m_ZonedBlocks = nativeList
		};
		CreateBlocksJob jobData2 = new CreateBlocksJob
		{
			m_BlockData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Zones_Block_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ZoneBlockDataData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ZoneBlockData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Cells = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Zones_Cell_RO_BufferLookup, ref base.CheckedStateRef),
			m_ZonedCells = zonedCells,
			m_ZonedBlocks = nativeList.AsDeferredJobArray(),
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
		};
		JobHandle jobHandle = JobChunkExtensions.Schedule(jobData, m_DefinitionQuery, JobHandle.CombineDependencies(base.Dependency, dependencies));
		JobHandle jobHandle2 = jobData2.Schedule(nativeList, 1, jobHandle);
		zonedCells.Dispose(jobHandle2);
		nativeList.Dispose(jobHandle2);
		m_ZoneSearchSystem.AddSearchTreeReader(jobHandle);
		m_ModificationBarrier.AddJobHandleForProducer(jobHandle2);
		base.Dependency = jobHandle2;
	}
```


## Nested types

- `Game.Tools.GenerateZonesSystem+CellData`  
- `Game.Tools.GenerateZonesSystem+BaseCell`  
- `Game.Tools.GenerateZonesSystem+FillBlocksListJob`  
- `Game.Tools.GenerateZonesSystem+CreateBlocksJob`  
- `Game.Tools.GenerateZonesSystem+TypeHandle`  

