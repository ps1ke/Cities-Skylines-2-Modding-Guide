# Game.Rendering.NotificationIconLocationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NotificationIconLocationSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_IconQuery;
    private Game.Rendering.NotificationIconLocationSystem+TypeHandle __TypeHandle;

    public NotificationIconLocationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_IconQuery`  

```csharp
private Unity.Entities.EntityQuery m_IconQuery;
```

- `private Game.Rendering.NotificationIconLocationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.NotificationIconLocationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public NotificationIconLocationSystem()`  

```csharp
[Preserve]
	public NotificationIconLocationSystem()
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
		m_IconQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadWrite<Icon>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<DisallowCluster>(),
				ComponentType.ReadOnly<Game.Notifications.Animation>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Deleted>() }
		});
		RequireForUpdate(m_IconQuery);
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
		JobHandle dependency = JobChunkExtensions.ScheduleParallel(new NotificationIconMoveJob
		{
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_IconType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Notifications_Icon_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InterpolatedTransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Rendering_InterpolatedTransform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef)
		}, m_IconQuery, base.Dependency);
		base.Dependency = dependency;
	}
```


## Nested types

- `Game.Rendering.NotificationIconLocationSystem+NotificationIconMoveJob`  
- `Game.Rendering.NotificationIconLocationSystem+TypeHandle`  

