# Game.Tools.AnimationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AnimationSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_AnimatedQuery;
    private Game.Tools.AnimationSystem+TypeHandle __TypeHandle;

    public AnimationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_AnimatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_AnimatedQuery;
```

- `private Game.Tools.AnimationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.AnimationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AnimationSystem()`  

```csharp
[Preserve]
	public AnimationSystem()
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
		m_AnimatedQuery = GetEntityQuery(ComponentType.ReadWrite<Animation>(), ComponentType.ReadOnly<Game.Objects.Transform>(), ComponentType.Exclude<Deleted>());
		RequireForUpdate(m_AnimatedQuery);
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
		JobHandle dependency = JobChunkExtensions.ScheduleParallel(new AnimateJob
		{
			m_DeltaTime = UnityEngine.Time.deltaTime,
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_AnimationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Animation_RW_ComponentTypeHandle, ref base.CheckedStateRef)
		}, m_AnimatedQuery, base.Dependency);
		base.Dependency = dependency;
	}
```


## Nested types

- `Game.Tools.AnimationSystem+AnimateJob`  
- `Game.Tools.AnimationSystem+TypeHandle`  

