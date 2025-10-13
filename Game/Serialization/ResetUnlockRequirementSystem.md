# Game.Serialization.ResetUnlockRequirementSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ResetUnlockRequirementSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_RequirementQuery;
    private Game.Serialization.ResetUnlockRequirementSystem+TypeHandle __TypeHandle;

    public ResetUnlockRequirementSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_RequirementQuery`  

```csharp
private Unity.Entities.EntityQuery m_RequirementQuery;
```

- `private Game.Serialization.ResetUnlockRequirementSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.ResetUnlockRequirementSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ResetUnlockRequirementSystem()`  

```csharp
[Preserve]
	public ResetUnlockRequirementSystem()
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
		m_RequirementQuery = GetEntityQuery(ComponentType.ReadOnly<UnlockRequirementData>());
		RequireForUpdate(m_RequirementQuery);
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
		ResetUnlockRequirementJob jobData = new ResetUnlockRequirementJob
		{
			m_UnlockRequirementDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_UnlockRequirementData_RW_ComponentTypeHandle, ref base.CheckedStateRef)
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_RequirementQuery, base.Dependency);
	}
```


## Nested types

- `Game.Serialization.ResetUnlockRequirementSystem+ResetUnlockRequirementJob`  
- `Game.Serialization.ResetUnlockRequirementSystem+TypeHandle`  

