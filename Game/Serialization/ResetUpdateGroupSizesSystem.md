# Game.Serialization.ResetUpdateGroupSizesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ResetUpdateGroupSizesSystem : Game.GameSystemBase
{
    private Game.Simulation.UpdateGroupSystem m_UpdateGroupSystem;
    private Game.Simulation.UpdateGroupSystem+UpdateGroupTypes m_UpdateGroupTypes;
    private Unity.Entities.EntityQuery m_UpdateFrameQuery;
    private Game.Serialization.ResetUpdateGroupSizesSystem+TypeHandle __TypeHandle;

    public ResetUpdateGroupSizesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.UpdateGroupSystem m_UpdateGroupSystem`  

```csharp
private Game.Simulation.UpdateGroupSystem m_UpdateGroupSystem;
```

- `private Game.Simulation.UpdateGroupSystem+UpdateGroupTypes m_UpdateGroupTypes`  

```csharp
private Game.Simulation.UpdateGroupSystem+UpdateGroupTypes m_UpdateGroupTypes;
```

- `private Unity.Entities.EntityQuery m_UpdateFrameQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdateFrameQuery;
```

- `private Game.Serialization.ResetUpdateGroupSizesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.ResetUpdateGroupSizesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ResetUpdateGroupSizesSystem()`  

```csharp
[Preserve]
	public ResetUpdateGroupSizesSystem()
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
		m_UpdateGroupSystem = base.World.GetOrCreateSystemManaged<UpdateGroupSystem>();
		m_UpdateFrameQuery = GetEntityQuery(ComponentType.ReadOnly<UpdateFrame>());
		m_UpdateGroupTypes = new UpdateGroupSystem.UpdateGroupTypes(this);
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
		NativeList<ArchetypeChunk> chunks = m_UpdateFrameQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		m_UpdateGroupTypes.Update(this);
		JobHandle jobHandle = IJobExtensions.Schedule(new ResetUpdateGroupSizesJob
		{
			m_Chunks = chunks,
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_UpdateGroupTypes = m_UpdateGroupTypes,
			m_UpdateGroupSizes = m_UpdateGroupSystem.GetUpdateGroupSizes()
		}, JobHandle.CombineDependencies(base.Dependency, outJobHandle));
		chunks.Dispose(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Serialization.ResetUpdateGroupSizesSystem+ResetUpdateGroupSizesJob`  
- `Game.Serialization.ResetUpdateGroupSizesSystem+TypeHandle`  

