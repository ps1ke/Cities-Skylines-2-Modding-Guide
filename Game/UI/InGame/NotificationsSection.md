# Game.UI.InGame.NotificationsSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NotificationsSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.UI.ImageSystem m_ImageSystem;
    private Unity.Entities.EntityQuery m_CitizenQuery;
    private System.Collections.Generic.List<Game.UI.InGame.NotificationInfo> <notifications>k__BackingField;
    private Unity.Collections.NativeList<Game.UI.InGame.Notification> m_NotificationsResult;
    private Unity.Collections.NativeArray<System.Boolean> m_DisplayResult;
    private Game.UI.InGame.NotificationsSection+TypeHandle __TypeHandle;

    protected System.String group { protected get; }
    protected System.Boolean displayForDestroyedObjects { protected get; }
    protected System.Boolean displayForOutsideConnections { protected get; }
    protected System.Boolean displayForUnderConstruction { protected get; }
    protected System.Boolean displayForUpgrades { protected get; }
    private System.Collections.Generic.List<Game.UI.InGame.NotificationInfo> notifications { private get; private set; }

    public NotificationsSection();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static Unity.Collections.NativeList<Game.UI.InGame.Notification> GetNotifications(Unity.Entities.EntityManager EntityManager, Unity.Entities.Entity entity, Unity.Collections.NativeList<Game.UI.InGame.Notification> notifications);
    public static Unity.Collections.NativeList<Game.UI.InGame.Notification> GetNotifications(Unity.Entities.Entity entity, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefDataFromEntity, Unity.Entities.ComponentLookup<Game.Notifications.Icon> iconDataFromEntity, Unity.Entities.BufferLookup<Game.Notifications.IconElement> iconBufferFromEntity, Unity.Collections.NativeList<Game.UI.InGame.Notification> notifications);
    public static System.Boolean HasNotifications(Unity.Entities.Entity entity, Unity.Entities.BufferLookup<Game.Notifications.IconElement> iconBuffer, Unity.Entities.ComponentLookup<Game.Notifications.Icon> iconDataFromEntity);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
}
```


## Fields

- `private Game.UI.ImageSystem m_ImageSystem`  

```csharp
private Game.UI.ImageSystem m_ImageSystem;
```

- `private Unity.Entities.EntityQuery m_CitizenQuery`  

```csharp
private Unity.Entities.EntityQuery m_CitizenQuery;
```

- `private System.Collections.Generic.List<Game.UI.InGame.NotificationInfo> <notifications>k__BackingField`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.NotificationInfo> <notifications>k__BackingField;
```

- `private Unity.Collections.NativeList<Game.UI.InGame.Notification> m_NotificationsResult`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.Notification> m_NotificationsResult;
```

- `private Unity.Collections.NativeArray<System.Boolean> m_DisplayResult`  

```csharp
private Unity.Collections.NativeArray<System.Boolean> m_DisplayResult;
```

- `private Game.UI.InGame.NotificationsSection+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.NotificationsSection+TypeHandle __TypeHandle;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `protected System.Boolean displayForDestroyedObjects { protected get }`  

```csharp
protected System.Boolean displayForDestroyedObjects { protected get; }
```

- `protected System.Boolean displayForOutsideConnections { protected get }`  

```csharp
protected System.Boolean displayForOutsideConnections { protected get; }
```

- `protected System.Boolean displayForUnderConstruction { protected get }`  

```csharp
protected System.Boolean displayForUnderConstruction { protected get; }
```

- `protected System.Boolean displayForUpgrades { protected get }`  

```csharp
protected System.Boolean displayForUpgrades { protected get; }
```

- `private System.Collections.Generic.List<Game.UI.InGame.NotificationInfo> notifications { private get; private set }`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.NotificationInfo> notifications { private get; private set; }
```


## Constructors

- `public NotificationsSection()`  

```csharp
[Preserve]
	public NotificationsSection()
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

- `public static GetNotifications(Unity.Entities.EntityManager EntityManager, Unity.Entities.Entity entity, Unity.Collections.NativeList<Game.UI.InGame.Notification> notifications) : Unity.Collections.NativeList<Game.UI.InGame.Notification>`  

```csharp
public static NativeList<Notification> GetNotifications(Entity entity, ComponentLookup<PrefabRef> prefabRefDataFromEntity, ComponentLookup<Icon> iconDataFromEntity, BufferLookup<IconElement> iconBufferFromEntity, NativeList<Notification> notifications)
	{
		if (iconBufferFromEntity.HasBuffer(entity))
		{
			DynamicBuffer<IconElement> dynamicBuffer = iconBufferFromEntity[entity];
			for (int i = 0; i < dynamicBuffer.Length; i++)
			{
				Entity icon = dynamicBuffer[i].m_Icon;
				if (iconDataFromEntity.HasComponent(icon))
				{
					Icon icon2 = iconDataFromEntity[icon];
					if (icon2.m_ClusterLayer != IconClusterLayer.Marker && prefabRefDataFromEntity.HasComponent(icon))
					{
						notifications.Add(new Notification(prefabRefDataFromEntity[icon].m_Prefab, entity, icon2.m_Priority));
					}
				}
			}
		}
		return notifications;
	}
```

- `public static GetNotifications(Unity.Entities.Entity entity, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefDataFromEntity, Unity.Entities.ComponentLookup<Game.Notifications.Icon> iconDataFromEntity, Unity.Entities.BufferLookup<Game.Notifications.IconElement> iconBufferFromEntity, Unity.Collections.NativeList<Game.UI.InGame.Notification> notifications) : Unity.Collections.NativeList<Game.UI.InGame.Notification>`  

```csharp
public static NativeList<Notification> GetNotifications(Entity entity, ComponentLookup<PrefabRef> prefabRefDataFromEntity, ComponentLookup<Icon> iconDataFromEntity, BufferLookup<IconElement> iconBufferFromEntity, NativeList<Notification> notifications)
	{
		if (iconBufferFromEntity.HasBuffer(entity))
		{
			DynamicBuffer<IconElement> dynamicBuffer = iconBufferFromEntity[entity];
			for (int i = 0; i < dynamicBuffer.Length; i++)
			{
				Entity icon = dynamicBuffer[i].m_Icon;
				if (iconDataFromEntity.HasComponent(icon))
				{
					Icon icon2 = iconDataFromEntity[icon];
					if (icon2.m_ClusterLayer != IconClusterLayer.Marker && prefabRefDataFromEntity.HasComponent(icon))
					{
						notifications.Add(new Notification(prefabRefDataFromEntity[icon].m_Prefab, entity, icon2.m_Priority));
					}
				}
			}
		}
		return notifications;
	}
```

- `public static HasNotifications(Unity.Entities.Entity entity, Unity.Entities.BufferLookup<Game.Notifications.IconElement> iconBuffer, Unity.Entities.ComponentLookup<Game.Notifications.Icon> iconDataFromEntity) : System.Boolean`  

```csharp
public static bool HasNotifications(Entity entity, BufferLookup<IconElement> iconBuffer, ComponentLookup<Icon> iconDataFromEntity)
	{
		if (iconBuffer.HasBuffer(entity))
		{
			DynamicBuffer<IconElement> dynamicBuffer = iconBuffer[entity];
			for (int i = 0; i < dynamicBuffer.Length; i++)
			{
				Entity icon = dynamicBuffer[i].m_Icon;
				if (iconDataFromEntity.HasComponent(icon) && iconDataFromEntity[icon].m_ClusterLayer != IconClusterLayer.Marker)
				{
					return true;
				}
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
		m_ImageSystem = base.World.GetOrCreateSystemManaged<ImageSystem>();
		m_CitizenQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<CurrentBuilding>(),
				ComponentType.ReadOnly<IconElement>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_DisplayResult = new NativeArray<bool>(1, Allocator.Persistent);
		m_NotificationsResult = new NativeList<Notification>(10, Allocator.Persistent);
		notifications = new List<NotificationInfo>(10);
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
		m_NotificationsResult.Dispose();
		m_DisplayResult.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		for (int i = 0; i < m_NotificationsResult.Length; i++)
		{
			NotificationInfo notificationInfo = new NotificationInfo(m_NotificationsResult[i]);
			bool flag = false;
			for (int j = 0; j < notifications.Count; j++)
			{
				if (notifications[j].entity == notificationInfo.entity)
				{
					if (base.EntityManager.HasComponent<Building>(selectedEntity))
					{
						notifications[j].AddTarget(notificationInfo.target);
					}
					flag = true;
				}
			}
			if (!flag)
			{
				notifications.Add(notificationInfo);
			}
		}
		notifications.Sort();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		IJobExtensions.Schedule(new CheckAndCacheNotificationsJob
		{
			m_Entity = selectedEntity,
			m_CitizenDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef),
			m_IconDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Notifications_Icon_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_IconElementBufferFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Notifications_IconElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_EmployeeBufferFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Companies_Employee_RO_BufferLookup, ref base.CheckedStateRef),
			m_RenterBufferFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferLookup, ref base.CheckedStateRef),
			m_HouseholdCitizenBufferFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
			m_RouteWaypointBufferFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteWaypoint_RO_BufferLookup, ref base.CheckedStateRef),
			m_DisplayResult = m_DisplayResult,
			m_NotificationResult = m_NotificationsResult
		}, base.Dependency).Complete();
		JobChunkExtensions.Schedule(new CheckAndCacheVisitorNotificationsJob
		{
			m_Entity = selectedEntity,
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_CurrentBuildingTypeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_CurrentBuilding_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_IconElementBufferFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Notifications_IconElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_IconDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Notifications_Icon_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RW_ComponentLookup, ref base.CheckedStateRef),
			m_DisplayResult = m_DisplayResult,
			m_NotificationResult = m_NotificationsResult
		}, m_CitizenQuery, base.Dependency).Complete();
		base.visible = m_DisplayResult[0];
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("notifications");
		writer.ArrayBegin(notifications.Count);
		for (int i = 0; i < notifications.Count; i++)
		{
			Entity entity = notifications[i].entity;
			writer.TypeBegin(typeof(Notification).FullName);
			writer.PropertyName("key");
			writer.Write(m_PrefabSystem.GetPrefabName(entity));
			writer.PropertyName("count");
			writer.Write(notifications[i].count);
			writer.PropertyName("iconPath");
			if (m_PrefabSystem.TryGetPrefab<PrefabBase>(entity, out var prefab))
			{
				writer.Write(ImageSystem.GetIcon(prefab) ?? m_ImageSystem.placeholderIcon);
			}
			else
			{
				writer.Write(m_ImageSystem.placeholderIcon);
			}
			writer.TypeEnd();
		}
		writer.ArrayEnd();
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		notifications.Clear();
		m_NotificationsResult.Clear();
		m_DisplayResult[0] = false;
	}
```


## Nested types

- `Game.UI.InGame.NotificationsSection+CheckAndCacheNotificationsJob`  
- `Game.UI.InGame.NotificationsSection+CheckAndCacheVisitorNotificationsJob`  
- `Game.UI.InGame.NotificationsSection+TypeHandle`  

