# Game.Objects.ContainerClearSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ContainerClearSystem : Game.GameSystemBase
{
    private Game.Serialization.LoadGameSystem m_LoadGameSystem;
    private Unity.Entities.EntityQuery m_EntityQuery;
    private Unity.Entities.ComponentTypeSet m_SubTypes;
    private Game.Objects.ContainerClearSystem+TypeHandle __TypeHandle;

    public ContainerClearSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Serialization.LoadGameSystem m_LoadGameSystem`  

```csharp
private Game.Serialization.LoadGameSystem m_LoadGameSystem;
```

- `private Unity.Entities.EntityQuery m_EntityQuery`  

```csharp
private Unity.Entities.EntityQuery m_EntityQuery;
```

- `private Unity.Entities.ComponentTypeSet m_SubTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_SubTypes;
```

- `private Game.Objects.ContainerClearSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Objects.ContainerClearSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ContainerClearSystem()`  

```csharp
[Preserve]
	public ContainerClearSystem()
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
		m_LoadGameSystem = base.World.GetOrCreateSystemManaged<LoadGameSystem>();
		m_EntityQuery = GetEntityQuery(ComponentType.ReadOnly<SubObject>(), ComponentType.ReadOnly<Game.Net.SubNet>(), ComponentType.ReadOnly<Game.Areas.SubArea>(), ComponentType.ReadOnly<Object>(), ComponentType.Exclude<Building>());
		m_SubTypes = new ComponentTypeSet(ComponentType.ReadWrite<SubObject>(), ComponentType.ReadWrite<Game.Net.SubNet>(), ComponentType.ReadWrite<Game.Areas.SubArea>());
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
		if (m_LoadGameSystem.context.purpose == Purpose.NewGame)
		{
			EntityCommandBuffer entityCommandBuffer = new EntityCommandBuffer(Allocator.TempJob);
			JobChunkExtensions.ScheduleParallel(new ContainerClearJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_EffectOwnerType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Effects_EnabledEffect_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_SubObjectType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_SubNetType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_SubNet_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_SubAreaType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_SubArea_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_PrefabEffects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_Effect_RO_BufferLookup, ref base.CheckedStateRef),
				m_PrefabSubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
				m_PrefabSubNets = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubNet_RO_BufferLookup, ref base.CheckedStateRef),
				m_PrefabSubAreas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubArea_RO_BufferLookup, ref base.CheckedStateRef),
				m_SubTypes = m_SubTypes,
				m_CommandBuffer = entityCommandBuffer.AsParallelWriter()
			}, m_EntityQuery, base.Dependency).Complete();
			entityCommandBuffer.Playback(base.EntityManager);
			entityCommandBuffer.Dispose();
		}
	}
```


## Nested types

- `Game.Objects.ContainerClearSystem+ContainerClearJob`  
- `Game.Objects.ContainerClearSystem+TypeHandle`  

