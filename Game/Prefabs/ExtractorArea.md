# Game.Prefabs.ExtractorArea

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ExtractorArea : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Areas.MapFeature m_MapFeature;
    public System.Single m_ObjectSpawnFactor;
    public System.Single m_MaxObjectArea;
    public System.Boolean m_RequireNaturalResource;
    public System.Single m_WorkAmountFactor;

    public ExtractorArea();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Areas.MapFeature m_MapFeature`  

```csharp
public Game.Areas.MapFeature m_MapFeature;
```

- `public System.Single m_ObjectSpawnFactor`  

```csharp
public System.Single m_ObjectSpawnFactor;
```

- `public System.Single m_MaxObjectArea`  

```csharp
public System.Single m_MaxObjectArea;
```

- `public System.Boolean m_RequireNaturalResource`  

```csharp
public System.Boolean m_RequireNaturalResource;
```

- `public System.Single m_WorkAmountFactor`  

```csharp
public System.Single m_WorkAmountFactor;
```


## Constructors

- `public ExtractorArea()`  

```csharp
public ExtractorArea();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Extractor>());
		components.Add(ComponentType.ReadWrite<OwnedVehicle>());
		if (m_MapFeature == MapFeature.Forest)
		{
			components.Add(ComponentType.ReadWrite<WoodResource>());
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<ExtractorAreaData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		entityManager.SetComponentData(entity, new ExtractorAreaData
		{
			m_MapFeature = m_MapFeature,
			m_ObjectSpawnFactor = m_ObjectSpawnFactor,
			m_MaxObjectArea = m_MaxObjectArea,
			m_RequireNaturalResource = m_RequireNaturalResource,
			m_WorkAmountFactor = m_WorkAmountFactor
		});
	}
```


