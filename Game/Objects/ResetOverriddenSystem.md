# Game.Objects.ResetOverriddenSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ResetOverriddenSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_OverriddenQuery;
    private Game.Objects.ResetOverriddenSystem+TypeHandle __TypeHandle;

    public ResetOverriddenSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_OverriddenQuery`  

```csharp
private Unity.Entities.EntityQuery m_OverriddenQuery;
```

- `private Game.Objects.ResetOverriddenSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Objects.ResetOverriddenSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ResetOverriddenSystem()`  

```csharp
[Preserve]
	public ResetOverriddenSystem()
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
		m_OverriddenQuery = GetEntityQuery(ComponentType.ReadOnly<Updated>(), ComponentType.ReadOnly<Overridden>(), ComponentType.ReadWrite<Tree>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		RequireForUpdate(m_OverriddenQuery);
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
		JobHandle dependency = JobChunkExtensions.ScheduleParallel(new ResetOverriddenJob
		{
			m_TreeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Tree_RW_ComponentTypeHandle, ref base.CheckedStateRef)
		}, m_OverriddenQuery, base.Dependency);
		base.Dependency = dependency;
	}
```


## Nested types

- `Game.Objects.ResetOverriddenSystem+ResetOverriddenJob`  
- `Game.Objects.ResetOverriddenSystem+TypeHandle`  

