# Game.Serialization.EndPrefabSerializationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EndPrefabSerializationSystem : Game.GameSystemBase
{
    private Game.Serialization.SaveGameSystem m_SaveGameSystem;
    private Unity.Entities.EntityQuery m_LoadedPrefabsQuery;
    private Unity.Entities.EntityQuery m_ContentPrefabQuery;
    private Game.Serialization.EndPrefabSerializationSystem+TypeHandle __TypeHandle;

    public EndPrefabSerializationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Serialization.SaveGameSystem m_SaveGameSystem`  

```csharp
private Game.Serialization.SaveGameSystem m_SaveGameSystem;
```

- `private Unity.Entities.EntityQuery m_LoadedPrefabsQuery`  

```csharp
private Unity.Entities.EntityQuery m_LoadedPrefabsQuery;
```

- `private Unity.Entities.EntityQuery m_ContentPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_ContentPrefabQuery;
```

- `private Game.Serialization.EndPrefabSerializationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.EndPrefabSerializationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public EndPrefabSerializationSystem()`  

```csharp
[Preserve]
	public EndPrefabSerializationSystem()
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
		m_SaveGameSystem = base.World.GetOrCreateSystemManaged<SaveGameSystem>();
		m_LoadedPrefabsQuery = GetEntityQuery(ComponentType.ReadOnly<LoadedIndex>());
		m_ContentPrefabQuery = GetEntityQuery(ComponentType.ReadOnly<ContentData>(), ComponentType.ReadOnly<PrefabData>());
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
		if (m_SaveGameSystem.referencedContent.IsCreated)
		{
			m_SaveGameSystem.referencedContent.Dispose();
		}
		m_SaveGameSystem.referencedContent = m_ContentPrefabQuery.ToEntityArray(Allocator.Persistent);
		JobChunkExtensions.ScheduleParallel(new EndPrefabSerializationJob
		{
			m_LoadedIndexType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_LoadedIndex_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_PrefabDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabData_RW_ComponentTypeHandle, ref base.CheckedStateRef)
		}, m_LoadedPrefabsQuery, base.Dependency).Complete();
	}
```


## Nested types

- `Game.Serialization.EndPrefabSerializationSystem+EndPrefabSerializationJob`  
- `Game.Serialization.EndPrefabSerializationSystem+TypeHandle`  

