# Game.Prefabs.ResourceConnection

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ResourceConnection : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Economy.ResourceInEditor m_Resource;
    public Game.Prefabs.NotificationIconPrefab m_ConnectionWarningNotification;

    public ResourceConnection();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Economy.ResourceInEditor m_Resource`  

```csharp
public Game.Economy.ResourceInEditor m_Resource;
```

- `public Game.Prefabs.NotificationIconPrefab m_ConnectionWarningNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_ConnectionWarningNotification;
```


## Constructors

- `public ResourceConnection()`  

```csharp
public ResourceConnection();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		if (components.Contains(ComponentType.ReadWrite<Node>()))
		{
			components.Add(ComponentType.ReadWrite<Game.Net.ResourceConnection>());
		}
		else if (components.Contains(ComponentType.ReadWrite<Edge>()))
		{
			components.Add(ComponentType.ReadWrite<Game.Net.ResourceConnection>());
		}
		else if (components.Contains(ComponentType.ReadWrite<Game.Objects.Object>()))
		{
			components.Add(ComponentType.ReadWrite<Game.Net.ResourceConnection>());
		}
	}
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		if (m_ConnectionWarningNotification != null)
		{
			prefabs.Add(m_ConnectionWarningNotification);
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<ResourceConnectionData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem orCreateSystemManaged = entityManager.World.GetOrCreateSystemManaged<PrefabSystem>();
		ResourceConnectionData componentData = new ResourceConnectionData
		{
			m_Resource = EconomyUtils.GetResource(m_Resource)
		};
		if (m_ConnectionWarningNotification != null)
		{
			componentData.m_ConnectionWarningNotification = orCreateSystemManaged.GetEntity(m_ConnectionWarningNotification);
		}
		entityManager.SetComponentData(entity, componentData);
	}
```


