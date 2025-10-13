# Game.Prefabs.NetCompositionMeshRefSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NetCompositionMeshRefSystem : Game.GameSystemBase
{
    private Game.Prefabs.NetCompositionMeshSystem m_NetCompositionMeshSystem;
    private Game.Common.ModificationBarrier4 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_CompositionQuery;
    private Unity.Entities.EntityArchetype m_MeshArchetype;
    private Game.Prefabs.NetCompositionMeshRefSystem+TypeHandle __TypeHandle;

    public NetCompositionMeshRefSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.NetCompositionMeshSystem m_NetCompositionMeshSystem`  

```csharp
private Game.Prefabs.NetCompositionMeshSystem m_NetCompositionMeshSystem;
```

- `private Game.Common.ModificationBarrier4 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_CompositionQuery`  

```csharp
private Unity.Entities.EntityQuery m_CompositionQuery;
```

- `private Unity.Entities.EntityArchetype m_MeshArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_MeshArchetype;
```

- `private Game.Prefabs.NetCompositionMeshRefSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.NetCompositionMeshRefSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public NetCompositionMeshRefSystem()`  

```csharp
[Preserve]
	public NetCompositionMeshRefSystem()
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
		m_NetCompositionMeshSystem = base.World.GetOrCreateSystemManaged<NetCompositionMeshSystem>();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier4>();
		m_CompositionQuery = GetEntityQuery(ComponentType.ReadOnly<NetCompositionData>(), ComponentType.ReadOnly<NetCompositionPiece>(), ComponentType.ReadOnly<NetCompositionMeshRef>(), ComponentType.ReadOnly<Created>());
		m_MeshArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<NetCompositionMeshData>(), ComponentType.ReadWrite<NetCompositionPiece>(), ComponentType.ReadWrite<MeshMaterial>(), ComponentType.ReadWrite<BatchGroup>(), ComponentType.ReadWrite<Created>(), ComponentType.ReadWrite<Updated>());
		RequireForUpdate(m_CompositionQuery);
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
		JobHandle outJobHandle;
		NativeList<ArchetypeChunk> chunks = m_CompositionQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		JobHandle dependencies;
		JobHandle jobHandle = IJobExtensions.Schedule(new CompositionMeshRefJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_CompositionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_NetCompositionData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_MeshData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_MeshData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CompositionMeshData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionMeshData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CompositionPieces = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionPiece_RO_BufferLookup, ref base.CheckedStateRef),
			m_LodMeshes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_LodMesh_RO_BufferLookup, ref base.CheckedStateRef),
			m_MeshMaterials = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_MeshMaterial_RO_BufferLookup, ref base.CheckedStateRef),
			m_Chunks = chunks,
			m_MeshArchetype = m_MeshArchetype,
			m_MeshEntities = m_NetCompositionMeshSystem.GetMeshEntities(out dependencies),
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer()
		}, JobHandle.CombineDependencies(base.Dependency, outJobHandle, dependencies));
		chunks.Dispose(jobHandle);
		m_NetCompositionMeshSystem.AddMeshEntityReader(jobHandle);
		m_ModificationBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Prefabs.NetCompositionMeshRefSystem+NewMeshData`  
- `Game.Prefabs.NetCompositionMeshRefSystem+CompositionMeshRefJob`  
- `Game.Prefabs.NetCompositionMeshRefSystem+TypeHandle`  

