# Game.Triggers.NotificationTriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Triggers`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NotificationTriggerSystem : Game.GameSystemBase
{
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Unity.Entities.EntityQuery m_CreatedNotificationsQuery;
    private Unity.Entities.EntityQuery m_DeletedNotificationsQuery;
    private Unity.Entities.EntityQuery m_AllNotificationsQuery;
    private Game.Triggers.NotificationTriggerSystem+TypeHandle __TypeHandle;

    public NotificationTriggerSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Unity.Entities.EntityQuery m_CreatedNotificationsQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedNotificationsQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedNotificationsQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedNotificationsQuery;
```

- `private Unity.Entities.EntityQuery m_AllNotificationsQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllNotificationsQuery;
```

- `private Game.Triggers.NotificationTriggerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Triggers.NotificationTriggerSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public NotificationTriggerSystem()`  

```csharp
[Preserve]
	public NotificationTriggerSystem()
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
		m_TriggerSystem = base.World.GetOrCreateSystemManaged<TriggerSystem>();
		m_CreatedNotificationsQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Icon>(),
				ComponentType.ReadOnly<PrefabRef>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Applied>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_DeletedNotificationsQuery = GetEntityQuery(ComponentType.ReadOnly<Icon>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<Deleted>(), ComponentType.Exclude<Temp>());
		m_AllNotificationsQuery = GetEntityQuery(ComponentType.ReadOnly<Icon>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		base.Enabled = false;
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

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected override void OnGamePreload(Purpose purpose, GameMode mode)
	{
		base.OnGamePreload(purpose, mode);
		base.Enabled = mode.IsGame();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		TriggerJob jobData = new TriggerJob
		{
			m_Created = m_CreatedNotificationsQuery.ToEntityArray(Allocator.TempJob),
			m_CreatedPrefabRefs = m_CreatedNotificationsQuery.ToComponentDataArray<PrefabRef>(Allocator.TempJob),
			m_Deleted = m_DeletedNotificationsQuery.ToEntityArray(Allocator.TempJob),
			m_DeletedPrefabRefs = m_DeletedNotificationsQuery.ToComponentDataArray<PrefabRef>(Allocator.TempJob),
			m_AllPrefabRefs = m_AllNotificationsQuery.ToComponentDataArray<PrefabRef>(Allocator.TempJob),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TargetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Target_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ActionQueue = m_TriggerSystem.CreateActionBuffer()
		};
		base.Dependency = IJobExtensions.Schedule(jobData, base.Dependency);
		m_TriggerSystem.AddActionBufferWriter(base.Dependency);
	}
```


## Nested types

- `Game.Triggers.NotificationTriggerSystem+TriggerJob`  
- `Game.Triggers.NotificationTriggerSystem+TypeHandle`  

