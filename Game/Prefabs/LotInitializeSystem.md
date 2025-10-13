# Game.Prefabs.LotInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LotInitializeSystem : Game.GameSystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Game.Prefabs.LotInitializeSystem+TypeHandle __TypeHandle;

    public LotInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Game.Prefabs.LotInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.LotInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public LotInitializeSystem()`  

```csharp
[Preserve]
	public LotInitializeSystem()
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
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_PrefabQuery = GetEntityQuery(ComponentType.ReadOnly<Created>(), ComponentType.ReadOnly<PrefabData>(), ComponentType.ReadOnly<LotData>(), ComponentType.ReadWrite<AreaGeometryData>());
		RequireAnyForUpdate(m_PrefabQuery);
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
		JobHandle dependency = JobChunkExtensions.ScheduleParallel(new InitializeLotPrefabsJob
		{
			m_SubObjectType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_SubObject_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_AreaGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_AreaGeometryData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PlaceholderObjectElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_PlaceholderObjectElement_RO_BufferLookup, ref base.CheckedStateRef)
		}, m_PrefabQuery, base.Dependency);
		base.Dependency = dependency;
	}
```


## Nested types

- `Game.Prefabs.LotInitializeSystem+InitializeLotPrefabsJob`  
- `Game.Prefabs.LotInitializeSystem+TypeHandle`  

