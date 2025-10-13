# Game.Prefabs.ResourceProducer

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `Game.Prefabs.IServiceUpgrade`  

**Attributes:** `ComponentMenu`, `RequireComponent`  

## Code

```csharp
public class ResourceProducer : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, Game.Prefabs.IServiceUpgrade
{
    public Game.Prefabs.ResourceProductionInfo[] m_Resources;

    public ResourceProducer();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public System.Void GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.ResourceProductionInfo[] m_Resources`  

```csharp
public Game.Prefabs.ResourceProductionInfo[] m_Resources;
```


## Constructors

- `public ResourceProducer()`  

```csharp
public ResourceProducer();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		if (GetComponent<ServiceUpgrade>() == null)
		{
			components.Add(ComponentType.ReadWrite<Game.Economy.Resources>());
			components.Add(ComponentType.ReadWrite<Game.Buildings.ResourceProducer>());
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<ResourceProductionData>());
	}
```

- `public GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public void GetUpgradeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Economy.Resources>());
		components.Add(ComponentType.ReadWrite<Game.Buildings.ResourceProducer>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		if (m_Resources != null)
		{
			DynamicBuffer<ResourceProductionData> buffer = entityManager.GetBuffer<ResourceProductionData>(entity);
			buffer.ResizeUninitialized(m_Resources.Length);
			for (int i = 0; i < m_Resources.Length; i++)
			{
				ResourceProductionInfo resourceProductionInfo = m_Resources[i];
				buffer[i] = new ResourceProductionData(EconomyUtils.GetResource(resourceProductionInfo.m_Resource), resourceProductionInfo.m_ProductionRate, resourceProductionInfo.m_StorageCapacity);
			}
		}
	}
```


