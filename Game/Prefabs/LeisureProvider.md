# Game.Prefabs.LeisureProvider

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class LeisureProvider : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Int32 m_Efficiency;
    public Game.Economy.ResourceInEditor m_Resources;
    public Game.Agents.LeisureType m_LeisureType;

    public LeisureProvider();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Int32 m_Efficiency`  

```csharp
public System.Int32 m_Efficiency;
```

- `public Game.Economy.ResourceInEditor m_Resources`  

```csharp
public Game.Economy.ResourceInEditor m_Resources;
```

- `public Game.Agents.LeisureType m_LeisureType`  

```csharp
public Game.Agents.LeisureType m_LeisureType;
```


## Constructors

- `public LeisureProvider()`  

```csharp
public LeisureProvider();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		if (m_Efficiency > 0)
		{
			components.Add(ComponentType.ReadWrite<Game.Buildings.LeisureProvider>());
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<LeisureProviderData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		entityManager.SetComponentData(entity, new LeisureProviderData
		{
			m_Efficiency = m_Efficiency,
			m_Resources = EconomyUtils.GetResource(m_Resources),
			m_LeisureType = m_LeisureType
		});
	}
```


