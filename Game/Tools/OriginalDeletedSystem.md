# Game.Tools.OriginalDeletedSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class OriginalDeletedSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_TempQuery;
    private Unity.Collections.NativeArray<System.Boolean> m_OriginalDeleted;
    private Unity.Jobs.JobHandle m_Dependency;
    private Game.Tools.OriginalDeletedSystem+TypeHandle __TypeHandle;

    public OriginalDeletedSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Boolean GetOriginalDeletedResult(System.Int32 delay);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_TempQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempQuery;
```

- `private Unity.Collections.NativeArray<System.Boolean> m_OriginalDeleted`  

```csharp
private Unity.Collections.NativeArray<System.Boolean> m_OriginalDeleted;
```

- `private Unity.Jobs.JobHandle m_Dependency`  

```csharp
private Unity.Jobs.JobHandle m_Dependency;
```

- `private Game.Tools.OriginalDeletedSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.OriginalDeletedSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public OriginalDeletedSystem()`  

```csharp
[Preserve]
	public OriginalDeletedSystem()
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

- `public GetOriginalDeletedResult(System.Int32 delay) : System.Boolean`  

```csharp
public bool GetOriginalDeletedResult(int delay)
	{
		m_Dependency.Complete();
		for (int num = 1 - delay; num >= 0; num--)
		{
			if (m_OriginalDeleted[num])
			{
				return true;
			}
		}
		return false;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_TempQuery = GetEntityQuery(ComponentType.ReadOnly<Temp>(), ComponentType.Exclude<Deleted>());
		m_OriginalDeleted = new NativeArray<bool>(2, Allocator.Persistent);
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

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_OriginalDeleted.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_OriginalDeleted[0] = m_OriginalDeleted[1];
		m_OriginalDeleted[1] = false;
		if (!m_TempQuery.IsEmptyIgnoreFilter)
		{
			base.Dependency = (m_Dependency = JobChunkExtensions.ScheduleParallel(new OriginalDeletedJob
			{
				m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_DeletedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EntityLookup = InternalCompilerInterface.GetEntityStorageInfoLookup(ref __TypeHandle.__EntityStorageInfoLookup, ref base.CheckedStateRef),
				m_OriginalDeleted = m_OriginalDeleted
			}, m_TempQuery, base.Dependency));
		}
	}
```


## Nested types

- `Game.Tools.OriginalDeletedSystem+OriginalDeletedJob`  
- `Game.Tools.OriginalDeletedSystem+TypeHandle`  

