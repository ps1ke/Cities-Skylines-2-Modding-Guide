# Game.Rendering.MarkerIconSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MarkerIconSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Unity.Entities.Entity m_SelectedMarker;
    private Unity.Entities.Entity m_FollowedMarker;
    private Unity.Entities.Entity m_SelectedLocation;
    private Unity.Entities.Entity m_FollowedLocation;
    private Unity.Entities.EntityQuery m_ConfigurationQuery;
    private Unity.Entities.EntityQuery m_IconQuery;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Rendering.MarkerIconSystem+TypeHandle __TypeHandle;

    public MarkerIconSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void AdjustLocations(Unity.Mathematics.float3 selectedLocation, Unity.Mathematics.float3 followedLocation, Unity.Mathematics.float3 cameraPos, Unity.Mathematics.float3 cameraUp);
    private Unity.Entities.Entity CreateMarker(Unity.Entities.Entity target, Unity.Mathematics.float3 position, Game.Rendering.MarkerIconSystem+MarkerType markerType, System.Boolean skipAnimation);
    public System.Void Deserialize<TReader>(TReader reader);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    private System.Void RemoveMarker(Unity.Entities.Entity& marker, System.Boolean skipAnimation);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
    private System.Void UpdateMarker(Unity.Entities.Entity& marker, Unity.Entities.Entity target, Game.Rendering.MarkerIconSystem+MarkerType markerType, Unity.Mathematics.float3 position, System.Boolean skipAnimation);
}
```


## Fields

- `private Unity.Entities.Entity m_SelectedMarker`  

```csharp
private Unity.Entities.Entity m_SelectedMarker;
```

- `private Unity.Entities.Entity m_FollowedMarker`  

```csharp
private Unity.Entities.Entity m_FollowedMarker;
```

- `private Unity.Entities.Entity m_SelectedLocation`  

```csharp
private Unity.Entities.Entity m_SelectedLocation;
```

- `private Unity.Entities.Entity m_FollowedLocation`  

```csharp
private Unity.Entities.Entity m_FollowedLocation;
```

- `private Unity.Entities.EntityQuery m_ConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigurationQuery;
```

- `private Unity.Entities.EntityQuery m_IconQuery`  

```csharp
private Unity.Entities.EntityQuery m_IconQuery;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Rendering.MarkerIconSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.MarkerIconSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public MarkerIconSystem()`  

```csharp
[Preserve]
	public MarkerIconSystem()
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

- `private AdjustLocations(Unity.Mathematics.float3 selectedLocation, Unity.Mathematics.float3 followedLocation, Unity.Mathematics.float3 cameraPos, Unity.Mathematics.float3 cameraUp) : System.Void`  

```csharp
private void AdjustLocations(float3 selectedLocation, float3 followedLocation, float3 cameraPos, float3 cameraUp)
	{
		NativeQueue<Overlap> overlapQueue = new NativeQueue<Overlap>(Allocator.TempJob);
		FindOverlapIconsJob jobData = new FindOverlapIconsJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_IconType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Notifications_Icon_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_Entity1 = m_SelectedMarker,
			m_Entity2 = m_FollowedMarker,
			m_Location1 = selectedLocation,
			m_Location2 = followedLocation,
			m_OverlapQueue = overlapQueue.AsParallelWriter()
		};
		UpdateMarkerLocationJob jobData2 = new UpdateMarkerLocationJob
		{
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_IconDisplayData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NotificationIconDisplayData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Entity1 = m_SelectedMarker,
			m_Entity2 = m_FollowedMarker,
			m_Location1 = selectedLocation,
			m_Location2 = followedLocation,
			m_CameraPos = cameraPos,
			m_CameraUp = cameraUp,
			m_IconData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Notifications_Icon_RW_ComponentLookup, ref base.CheckedStateRef),
			m_OverlapQueue = overlapQueue
		};
		JobHandle dependsOn = JobChunkExtensions.ScheduleParallel(jobData, m_IconQuery, base.Dependency);
		JobHandle jobHandle = IJobExtensions.Schedule(jobData2, dependsOn);
		overlapQueue.Dispose(jobHandle);
		base.Dependency = jobHandle;
	}
```

- `private CreateMarker(Unity.Entities.Entity target, Unity.Mathematics.float3 position, Game.Rendering.MarkerIconSystem+MarkerType markerType, System.Boolean skipAnimation) : Unity.Entities.Entity`  

```csharp
private Entity CreateMarker(Entity target, float3 position, MarkerType markerType, bool skipAnimation)
	{
		if (m_ConfigurationQuery.IsEmptyIgnoreFilter)
		{
			return Entity.Null;
		}
		Entity singletonEntity = m_ConfigurationQuery.GetSingletonEntity();
		IconConfigurationData componentData = base.EntityManager.GetComponentData<IconConfigurationData>(singletonEntity);
		Entity entity;
		switch (markerType)
		{
		case MarkerType.Selected:
			entity = componentData.m_SelectedMarker;
			break;
		case MarkerType.Followed:
			entity = componentData.m_FollowedMarker;
			break;
		default:
			return Entity.Null;
		}
		NotificationIconData componentData2 = base.EntityManager.GetComponentData<NotificationIconData>(entity);
		Icon componentData3 = new Icon
		{
			m_Priority = IconPriority.Info,
			m_Flags = (IconFlags.Unique | IconFlags.OnTop),
			m_Location = position
		};
		Entity entity2 = base.EntityManager.CreateEntity(componentData2.m_Archetype);
		base.EntityManager.SetComponentData(entity2, new PrefabRef(entity));
		base.EntityManager.SetComponentData(entity2, componentData3);
		base.EntityManager.AddComponentData(entity2, new Target(target));
		base.EntityManager.AddComponent<DisallowCluster>(entity2);
		if (!skipAnimation)
		{
			float duration = base.EntityManager.GetBuffer<IconAnimationElement>(singletonEntity, isReadOnly: true)[0].m_Duration;
			base.EntityManager.AddComponentData(entity2, new Game.Notifications.Animation(Game.Notifications.AnimationType.MarkerAppear, UnityEngine.Time.deltaTime, duration));
		}
		return entity2;
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_CameraUpdateSystem = base.World.GetOrCreateSystemManaged<CameraUpdateSystem>();
		m_ConfigurationQuery = GetEntityQuery(ComponentType.ReadOnly<IconConfigurationData>());
		m_IconQuery = GetEntityQuery(ComponentType.ReadOnly<Icon>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
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
		Entity entity = m_ToolSystem.selected;
		int elementIndex = m_ToolSystem.selectedIndex;
		Entity entity2 = Entity.Null;
		int elementIndex2 = -1;
		if (m_CameraUpdateSystem.orbitCameraController != null)
		{
			entity2 = m_CameraUpdateSystem.orbitCameraController.followedEntity;
		}
		float3 position = default(float3);
		float3 position2 = default(float3);
		Entity location = Entity.Null;
		Entity location2 = Entity.Null;
		Bounds3 bounds = default(Bounds3);
		Bounds3 bounds2 = default(Bounds3);
		if (entity2 != Entity.Null && !SelectedInfoUISystem.TryGetPosition(entity2, base.EntityManager, ref elementIndex2, out location, out position2, out bounds, out var rotation))
		{
			location = Entity.Null;
		}
		if ((entity2 == entity && elementIndex2 == elementIndex) || (base.EntityManager.TryGetComponent<CurrentTransport>(entity2, out var component) && component.m_CurrentTransport == entity))
		{
			entity = Entity.Null;
		}
		if (entity != Entity.Null && (!SelectedInfoUISystem.TryGetPosition(entity, base.EntityManager, ref elementIndex, out location2, out position, out bounds2, out rotation) || location == location2))
		{
			location2 = Entity.Null;
		}
		if (entity2 != Entity.Null)
		{
			if (location != m_FollowedLocation)
			{
				RemoveMarker(ref m_FollowedMarker, location2 == m_FollowedLocation);
			}
			position2.y = bounds.max.y;
			UpdateMarker(ref m_FollowedMarker, entity2, MarkerType.Followed, position2, m_SelectedLocation == location);
		}
		else
		{
			RemoveMarker(ref m_FollowedMarker, location2 == m_FollowedLocation);
		}
		if (entity != Entity.Null)
		{
			if (location2 != m_SelectedLocation)
			{
				RemoveMarker(ref m_SelectedMarker, location == m_SelectedLocation);
			}
			position.y = bounds2.max.y;
			UpdateMarker(ref m_SelectedMarker, entity, MarkerType.Selected, position, m_FollowedLocation == location2);
		}
		else
		{
			RemoveMarker(ref m_SelectedMarker, location == m_SelectedLocation);
		}
		m_FollowedLocation = location;
		m_SelectedLocation = location2;
		if ((m_SelectedMarker != Entity.Null || m_FollowedMarker != Entity.Null) && m_CameraUpdateSystem.activeCameraController != null)
		{
			AdjustLocations(position, position2, m_CameraUpdateSystem.activeCameraController.position, Quaternion.Euler(m_CameraUpdateSystem.activeCameraController.rotation) * Vector3.up);
		}
	}
```

- `private RemoveMarker(Unity.Entities.Entity& marker, System.Boolean skipAnimation) : System.Void`  

```csharp
private void RemoveMarker(ref Entity marker, bool skipAnimation)
	{
		if (!(marker != Entity.Null))
		{
			return;
		}
		Game.Notifications.Animation component;
		if (skipAnimation || m_ConfigurationQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<Deleted>(marker);
		}
		else if (base.EntityManager.TryGetComponent<Game.Notifications.Animation>(marker, out component))
		{
			if (component.m_Type != Game.Notifications.AnimationType.MarkerDisappear)
			{
				component.m_Type = Game.Notifications.AnimationType.MarkerDisappear;
				component.m_Timer = component.m_Duration - component.m_Timer;
				base.EntityManager.SetComponentData(marker, component);
			}
		}
		else
		{
			Entity singletonEntity = m_ConfigurationQuery.GetSingletonEntity();
			float duration = base.EntityManager.GetBuffer<IconAnimationElement>(singletonEntity, isReadOnly: true)[1].m_Duration;
			base.EntityManager.AddComponentData(marker, new Game.Notifications.Animation(Game.Notifications.AnimationType.MarkerDisappear, UnityEngine.Time.deltaTime, duration));
		}
		marker = Entity.Null;
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void SetDefaults(Context context)
	{
		m_SelectedMarker = Entity.Null;
		m_FollowedMarker = Entity.Null;
		m_SelectedLocation = Entity.Null;
		m_FollowedLocation = Entity.Null;
	}
```

- `private UpdateMarker(Unity.Entities.Entity& marker, Unity.Entities.Entity target, Game.Rendering.MarkerIconSystem+MarkerType markerType, Unity.Mathematics.float3 position, System.Boolean skipAnimation) : System.Void`  

```csharp
private void UpdateMarker(ref Entity marker, Entity target, MarkerType markerType, float3 position, bool skipAnimation)
	{
		if (base.EntityManager.HasComponent<Icon>(target) && base.EntityManager.TryGetComponent<Owner>(target, out var component) && base.EntityManager.Exists(component.m_Owner))
		{
			target = component.m_Owner;
		}
		if (marker == Entity.Null)
		{
			marker = CreateMarker(target, position, markerType, skipAnimation);
			return;
		}
		Target componentData = base.EntityManager.GetComponentData<Target>(marker);
		if (componentData.m_Target != target)
		{
			componentData.m_Target = target;
			base.EntityManager.SetComponentData(marker, componentData);
		}
	}
```


## Nested types

- `Game.Rendering.MarkerIconSystem+MarkerType`  
- `Game.Rendering.MarkerIconSystem+Overlap`  
- `Game.Rendering.MarkerIconSystem+FindOverlapIconsJob`  
- `Game.Rendering.MarkerIconSystem+UpdateMarkerLocationJob`  
- `Game.Rendering.MarkerIconSystem+TypeHandle`  

