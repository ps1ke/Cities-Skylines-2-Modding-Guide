# Game.Prefabs.AchievementFilter

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class AchievementFilter : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Colossal.PSI.Common.AchievementId[] m_ValidFor;
    public Colossal.PSI.Common.AchievementId[] m_NotValidFor;

    public AchievementFilter();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Colossal.PSI.Common.AchievementId[] m_ValidFor`  

```csharp
public Colossal.PSI.Common.AchievementId[] m_ValidFor;
```

- `public Colossal.PSI.Common.AchievementId[] m_NotValidFor`  

```csharp
public Colossal.PSI.Common.AchievementId[] m_NotValidFor;
```


## Constructors

- `public AchievementFilter()`  

```csharp
public AchievementFilter();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<AchievementFilterData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		DynamicBuffer<AchievementFilterData> buffer = entityManager.GetBuffer<AchievementFilterData>(entity);
		if (m_ValidFor != null)
		{
			for (int i = 0; i < m_ValidFor.Length; i++)
			{
				buffer.Add(new AchievementFilterData
				{
					m_AchievementID = m_ValidFor[i],
					m_Allow = true
				});
			}
		}
		if (m_NotValidFor != null)
		{
			for (int j = 0; j < m_NotValidFor.Length; j++)
			{
				buffer.Add(new AchievementFilterData
				{
					m_AchievementID = m_NotValidFor[j],
					m_Allow = false
				});
			}
		}
	}
```


