# Game.Prefabs.WorkProviderParameterPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class WorkProviderParameterPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.NotificationIconPrefab m_UneducatedNotificationPrefab;
    public Game.Prefabs.NotificationIconPrefab m_EducatedNotificationPrefab;
    public System.Int16 m_UneducatedNotificationDelay;
    public System.Int16 m_EducatedNotificationDelay;
    public System.Single m_UneducatedNotificationLimit;
    public System.Single m_EducatedNotificationLimit;
    public System.Int32 m_SeniorEmployeeLevel;

    public WorkProviderParameterPrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.NotificationIconPrefab m_UneducatedNotificationPrefab`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_UneducatedNotificationPrefab;
```

- `public Game.Prefabs.NotificationIconPrefab m_EducatedNotificationPrefab`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_EducatedNotificationPrefab;
```

- `public System.Int16 m_UneducatedNotificationDelay`  

```csharp
public System.Int16 m_UneducatedNotificationDelay;
```

- `public System.Int16 m_EducatedNotificationDelay`  

```csharp
public System.Int16 m_EducatedNotificationDelay;
```

- `public System.Single m_UneducatedNotificationLimit`  

```csharp
public System.Single m_UneducatedNotificationLimit;
```

- `public System.Single m_EducatedNotificationLimit`  

```csharp
public System.Single m_EducatedNotificationLimit;
```

- `public System.Int32 m_SeniorEmployeeLevel`  

```csharp
public System.Int32 m_SeniorEmployeeLevel;
```


## Constructors

- `public WorkProviderParameterPrefab()`  

```csharp
public WorkProviderParameterPrefab();
```


## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		prefabs.Add(m_UneducatedNotificationPrefab);
		prefabs.Add(m_EducatedNotificationPrefab);
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<WorkProviderParameterData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem orCreateSystemManaged = entityManager.World.GetOrCreateSystemManaged<PrefabSystem>();
		entityManager.SetComponentData(entity, new WorkProviderParameterData
		{
			m_EducatedNotificationPrefab = orCreateSystemManaged.GetEntity(m_EducatedNotificationPrefab),
			m_UneducatedNotificationPrefab = orCreateSystemManaged.GetEntity(m_UneducatedNotificationPrefab),
			m_EducatedNotificationDelay = m_EducatedNotificationDelay,
			m_EducatedNotificationLimit = m_EducatedNotificationLimit,
			m_UneducatedNotificationDelay = m_UneducatedNotificationDelay,
			m_UneducatedNotificationLimit = m_UneducatedNotificationLimit,
			m_SeniorEmployeeLevel = m_SeniorEmployeeLevel
		});
	}
```


