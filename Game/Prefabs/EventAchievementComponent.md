# Game.Prefabs.EventAchievementComponent

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class EventAchievementComponent : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.EventAchievementComponent+EventAchievementSetup[] m_Achievements;

    public EventAchievementComponent();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.EventAchievementComponent+EventAchievementSetup[] m_Achievements`  

```csharp
public Game.Prefabs.EventAchievementComponent+EventAchievementSetup[] m_Achievements;
```


## Constructors

- `public EventAchievementComponent()`  

```csharp
public EventAchievementComponent();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<EventAchievement>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<EventAchievementData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		DynamicBuffer<EventAchievementData> buffer = entityManager.GetBuffer<EventAchievementData>(entity);
		for (int i = 0; i < m_Achievements.Length; i++)
		{
			buffer.Add(new EventAchievementData
			{
				m_ID = m_Achievements[i].m_ID,
				m_FrameDelay = m_Achievements[i].m_FrameDelay,
				m_BypassCounter = m_Achievements[i].m_BypassCounter
			});
		}
	}
```


## Nested types

- `Game.Prefabs.EventAchievementComponent+EventAchievementSetup`  

