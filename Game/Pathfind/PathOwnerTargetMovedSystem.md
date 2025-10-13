# Game.Pathfind.PathOwnerTargetMovedSystem

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PathOwnerTargetMovedSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_EventQuery;
    private Unity.Entities.EntityQuery m_PathOwnerQuery;
    private Game.Pathfind.PathOwnerTargetMovedSystem+TypeHandle __TypeHandle;

    public PathOwnerTargetMovedSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_EventQuery`  

```csharp
private Unity.Entities.EntityQuery m_EventQuery;
```

- `private Unity.Entities.EntityQuery m_PathOwnerQuery`  

```csharp
private Unity.Entities.EntityQuery m_PathOwnerQuery;
```

- `private Game.Pathfind.PathOwnerTargetMovedSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Pathfind.PathOwnerTargetMovedSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public PathOwnerTargetMovedSystem()`  

```csharp
[Preserve]
	public PathOwnerTargetMovedSystem()
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
		m_EventQuery = GetEntityQuery(ComponentType.ReadOnly<PathTargetMoved>(), ComponentType.ReadOnly<Event>());
		m_PathOwnerQuery = GetEntityQuery(ComponentType.ReadOnly<PathOwner>(), ComponentType.ReadOnly<PathElement>(), ComponentType.ReadOnly<Target>(), ComponentType.Exclude<GroupMember>());
		RequireForUpdate(m_EventQuery);
		RequireForUpdate(m_PathOwnerQuery);
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
		NativeArray<PathTargetMoved> nativeArray = m_EventQuery.ToComponentDataArray<PathTargetMoved>(Allocator.TempJob);
		try
		{
			CheckPathOwnerTargetsJob jobData = new CheckPathOwnerTargetsJob
			{
				m_TargetType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Target_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PathOwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Pathfind_PathOwner_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PathElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Pathfind_PathElement_RW_BufferTypeHandle, ref base.CheckedStateRef)
			};
			for (int i = 0; i < nativeArray.Length; i++)
			{
				jobData.m_RandomSeed = RandomSeed.Next();
				jobData.m_MovedEntity = nativeArray[i].m_Target;
				base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_PathOwnerQuery, base.Dependency);
			}
		}
		finally
		{
			nativeArray.Dispose();
		}
	}
```


## Nested types

- `Game.Pathfind.PathOwnerTargetMovedSystem+CheckPathOwnerTargetsJob`  
- `Game.Pathfind.PathOwnerTargetMovedSystem+TypeHandle`  

