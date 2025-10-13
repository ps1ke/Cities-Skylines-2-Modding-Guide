# Game.Serialization.FilterLoadedSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class FilterLoadedSystem : Game.GameSystemBase
{
    private Game.Serialization.LoadGameSystem m_LoadGameSystem;
    private Unity.Entities.EntityQuery m_NetLaneQuery;
    private Unity.Entities.EntityQuery m_EditorContainerQuery;
    private Game.Serialization.FilterLoadedSystem+TypeHandle __TypeHandle;

    public FilterLoadedSystem();

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

- `private Unity.Entities.EntityQuery m_NetLaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_NetLaneQuery;
```

- `private Unity.Entities.EntityQuery m_EditorContainerQuery`  

```csharp
private Unity.Entities.EntityQuery m_EditorContainerQuery;
```

- `private Game.Serialization.FilterLoadedSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.FilterLoadedSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public FilterLoadedSystem()`  

```csharp
[Preserve]
	public FilterLoadedSystem()
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
		m_NetLaneQuery = GetEntityQuery(ComponentType.ReadOnly<Lane>(), ComponentType.ReadOnly<Owner>());
		m_EditorContainerQuery = GetEntityQuery(ComponentType.ReadOnly<EditorContainer>());
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
		if (m_LoadGameSystem.context.purpose == Purpose.NewGame && !m_EditorContainerQuery.IsEmptyIgnoreFilter)
		{
			if (!m_NetLaneQuery.IsEmptyIgnoreFilter)
			{
				EntityCommandBuffer entityCommandBuffer = new EntityCommandBuffer(Allocator.TempJob);
				JobChunkExtensions.ScheduleParallel(new CheckLanesJob
				{
					m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
					m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
					m_EditorContainerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_EditorContainer_RO_ComponentLookup, ref base.CheckedStateRef),
					m_CommandBuffer = entityCommandBuffer.AsParallelWriter()
				}, m_NetLaneQuery, base.Dependency).Complete();
				entityCommandBuffer.Playback(base.EntityManager);
				entityCommandBuffer.Dispose();
			}
			base.EntityManager.DestroyEntity(m_EditorContainerQuery);
		}
	}
```


## Nested types

- `Game.Serialization.FilterLoadedSystem+CheckLanesJob`  
- `Game.Serialization.FilterLoadedSystem+TypeHandle`  

