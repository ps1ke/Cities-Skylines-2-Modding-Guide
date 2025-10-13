# Game.Prefabs.ActivityLocationPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.TransformPrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ActivityLocationPrefab : Game.Prefabs.TransformPrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.ActivityType[] m_Activities;

    public ActivityLocationPrefab();

    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.ActivityType[] m_Activities`  

```csharp
public Game.Prefabs.ActivityType[] m_Activities;
```


## Constructors

- `public ActivityLocationPrefab()`  

```csharp
public ActivityLocationPrefab();
```


## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<ActivityLocationData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		ActivityLocationData componentData = default(ActivityLocationData);
		componentData.m_ActivityMask = default(ActivityMask);
		if (m_Activities != null)
		{
			for (int i = 0; i < m_Activities.Length; i++)
			{
				componentData.m_ActivityMask.m_Mask |= new ActivityMask(m_Activities[i]).m_Mask;
			}
		}
		entityManager.SetComponentData(entity, componentData);
	}
```


