# Game.Prefabs.ObjectAchievementComponent

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ObjectAchievementComponent : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.ObjectAchievementComponent+ObjectAchievementSetup[] m_Achievements;

    public ObjectAchievementComponent();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.ObjectAchievementComponent+ObjectAchievementSetup[] m_Achievements`  

```csharp
public Game.Prefabs.ObjectAchievementComponent+ObjectAchievementSetup[] m_Achievements;
```


## Constructors

- `public ObjectAchievementComponent()`  

```csharp
public ObjectAchievementComponent();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<ObjectAchievement>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<ObjectAchievementData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		DynamicBuffer<ObjectAchievementData> buffer = entityManager.GetBuffer<ObjectAchievementData>(entity);
		ObjectAchievementSetup[] achievements = m_Achievements;
		for (int i = 0; i < achievements.Length; i++)
		{
			ObjectAchievementSetup objectAchievementSetup = achievements[i];
			buffer.Add(new ObjectAchievementData
			{
				m_ID = objectAchievementSetup.m_ID,
				m_BypassCounter = objectAchievementSetup.m_BypassCounter,
				m_AbsoluteCounter = objectAchievementSetup.m_AbsoluteCounter
			});
		}
	}
```


## Nested types

- `Game.Prefabs.ObjectAchievementComponent+ObjectAchievementSetup`  

