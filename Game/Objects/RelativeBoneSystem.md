# Game.Objects.RelativeBoneSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RelativeBoneSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_EntityQuery;
    private Game.Objects.RelativeBoneSystem+TypeHandle __TypeHandle;

    public RelativeBoneSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_EntityQuery`  

```csharp
private Unity.Entities.EntityQuery m_EntityQuery;
```

- `private Game.Objects.RelativeBoneSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Objects.RelativeBoneSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public RelativeBoneSystem()`  

```csharp
[Preserve]
	public RelativeBoneSystem()
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
		m_EntityQuery = GetEntityQuery(ComponentType.ReadWrite<Relative>(), ComponentType.ReadOnly<Owner>());
		RequireForUpdate(m_EntityQuery);
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
		RelativeBoneJob jobData = new RelativeBoneJob
		{
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RelativeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Relative_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabSubMeshes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubMesh_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabProceduralBones = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ProceduralBone_RO_BufferLookup, ref base.CheckedStateRef)
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_EntityQuery, base.Dependency);
	}
```


## Nested types

- `Game.Objects.RelativeBoneSystem+RelativeBoneJob`  
- `Game.Objects.RelativeBoneSystem+TypeHandle`  

