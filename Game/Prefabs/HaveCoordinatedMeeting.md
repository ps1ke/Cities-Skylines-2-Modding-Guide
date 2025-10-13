# Game.Prefabs.HaveCoordinatedMeeting

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class HaveCoordinatedMeeting : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.CoordinatedMeetingPhase[] m_Phases;

    public HaveCoordinatedMeeting();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.CoordinatedMeetingPhase[] m_Phases`  

```csharp
public Game.Prefabs.CoordinatedMeetingPhase[] m_Phases;
```


## Constructors

- `public HaveCoordinatedMeeting()`  

```csharp
public HaveCoordinatedMeeting();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<CoordinatedMeeting>());
		components.Add(ComponentType.ReadWrite<CoordinatedMeetingAttendee>());
		components.Add(ComponentType.ReadWrite<TargetElement>());
		components.Add(ComponentType.ReadWrite<PrefabRef>());
	}
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		for (int i = 0; i < m_Phases.Length; i++)
		{
			if (m_Phases[i].m_Notification != null)
			{
				prefabs.Add(m_Phases[i].m_Notification);
			}
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<HaveCoordinatedMeetingData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		DynamicBuffer<HaveCoordinatedMeetingData> buffer = entityManager.GetBuffer<HaveCoordinatedMeetingData>(entity);
		if (m_Phases != null)
		{
			HaveCoordinatedMeetingData elem = default(HaveCoordinatedMeetingData);
			for (int i = 0; i < m_Phases.Length; i++)
			{
				CoordinatedMeetingPhase coordinatedMeetingPhase = m_Phases[i];
				TravelPurpose travelPurpose = new TravelPurpose
				{
					m_Purpose = coordinatedMeetingPhase.m_Purpose.m_Purpose,
					m_Data = coordinatedMeetingPhase.m_Purpose.m_Data,
					m_Resource = EconomyUtils.GetResource(coordinatedMeetingPhase.m_Purpose.m_Resource)
				};
				elem.m_TravelPurpose = travelPurpose;
				elem.m_Delay = coordinatedMeetingPhase.m_Delay;
				elem.m_Notification = ((coordinatedMeetingPhase.m_Notification != null) ? World.DefaultGameObjectInjectionWorld.GetOrCreateSystemManaged<PrefabSystem>().GetEntity(coordinatedMeetingPhase.m_Notification) : Entity.Null);
				buffer.Add(elem);
			}
		}
	}
```


