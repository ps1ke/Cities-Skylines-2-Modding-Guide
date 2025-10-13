# Game.Prefabs.CompanyNotificationParameterPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class CompanyNotificationParameterPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.NotificationIconPrefab m_NoInputsNotificationPrefab;
    public Game.Prefabs.NotificationIconPrefab m_NoCustomersNotificationPrefab;
    public System.Single m_NoInputCostLimit;
    public System.Single m_NoCustomersServiceLimit;
    public System.Single m_NoCustomersHotelLimit;

    public CompanyNotificationParameterPrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.NotificationIconPrefab m_NoInputsNotificationPrefab`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_NoInputsNotificationPrefab;
```

- `public Game.Prefabs.NotificationIconPrefab m_NoCustomersNotificationPrefab`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_NoCustomersNotificationPrefab;
```

- `public System.Single m_NoInputCostLimit`  

```csharp
public System.Single m_NoInputCostLimit;
```

- `public System.Single m_NoCustomersServiceLimit`  

```csharp
public System.Single m_NoCustomersServiceLimit;
```

- `public System.Single m_NoCustomersHotelLimit`  

```csharp
public System.Single m_NoCustomersHotelLimit;
```


## Constructors

- `public CompanyNotificationParameterPrefab()`  

```csharp
public CompanyNotificationParameterPrefab();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		base.GetArchetypeComponents(components);
	}
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		prefabs.Add(m_NoInputsNotificationPrefab);
		prefabs.Add(m_NoCustomersNotificationPrefab);
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<CompanyNotificationParameterData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem orCreateSystemManaged = entityManager.World.GetOrCreateSystemManaged<PrefabSystem>();
		CompanyNotificationParameterData componentData = default(CompanyNotificationParameterData);
		componentData.m_NoCustomersNotificationPrefab = orCreateSystemManaged.GetEntity(m_NoCustomersNotificationPrefab);
		componentData.m_NoInputsNotificationPrefab = orCreateSystemManaged.GetEntity(m_NoInputsNotificationPrefab);
		componentData.m_NoCustomersServiceLimit = m_NoCustomersServiceLimit;
		componentData.m_NoInputCostLimit = m_NoInputCostLimit;
		componentData.m_NoCustomersHotelLimit = m_NoCustomersHotelLimit;
		entityManager.SetComponentData(entity, componentData);
	}
```


