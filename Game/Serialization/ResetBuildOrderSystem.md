# Game.Serialization.ResetBuildOrderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ResetBuildOrderSystem : Game.GameSystemBase
{
    private Game.Tools.GenerateEdgesSystem m_GenerateEdgesSystem;
    private Unity.Entities.EntityQuery m_BuildOrderQuery;
    private Game.Serialization.ResetBuildOrderSystem+TypeHandle __TypeHandle;

    public ResetBuildOrderSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.GenerateEdgesSystem m_GenerateEdgesSystem`  

```csharp
private Game.Tools.GenerateEdgesSystem m_GenerateEdgesSystem;
```

- `private Unity.Entities.EntityQuery m_BuildOrderQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildOrderQuery;
```

- `private Game.Serialization.ResetBuildOrderSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.ResetBuildOrderSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ResetBuildOrderSystem()`  

```csharp
[Preserve]
	public ResetBuildOrderSystem()
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
		m_GenerateEdgesSystem = base.World.GetOrCreateSystemManaged<GenerateEdgesSystem>();
		m_BuildOrderQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Game.Net.BuildOrder>(),
				ComponentType.ReadOnly<Game.Zones.BuildOrder>()
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
		JobHandle outJobHandle;
		NativeList<ArchetypeChunk> chunks = m_BuildOrderQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		JobHandle jobHandle = IJobExtensions.Schedule(new ResetBuildOrderJob
		{
			m_Chunks = chunks,
			m_NetBuildOrderType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_BuildOrder_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ZoneBuildOrderType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Zones_BuildOrder_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BuildOrder = m_GenerateEdgesSystem.GetBuildOrder()
		}, JobHandle.CombineDependencies(base.Dependency, outJobHandle));
		chunks.Dispose(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Serialization.ResetBuildOrderSystem+ResetBuildOrderJob`  
- `Game.Serialization.ResetBuildOrderSystem+TypeHandle`  

