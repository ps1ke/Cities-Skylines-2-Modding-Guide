# Game.Prefabs.QuantityObject

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class QuantityObject : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Economy.ResourceInEditor[] m_Resources;
    public Game.Areas.MapFeature m_MapFeature;

    public QuantityObject();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Economy.ResourceInEditor[] m_Resources`  

```csharp
public Game.Economy.ResourceInEditor[] m_Resources;
```

- `public Game.Areas.MapFeature m_MapFeature`  

```csharp
public Game.Areas.MapFeature m_MapFeature;
```


## Constructors

- `public QuantityObject()`  

```csharp
public QuantityObject();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Quantity>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<QuantityObjectData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		QuantityObjectData componentData = default(QuantityObjectData);
		if (m_Resources != null)
		{
			for (int i = 0; i < m_Resources.Length; i++)
			{
				componentData.m_Resources |= EconomyUtils.GetResource(m_Resources[i]);
			}
		}
		componentData.m_MapFeature = m_MapFeature;
		entityManager.SetComponentData(entity, componentData);
		if (componentData.m_Resources == Resource.NoResource && componentData.m_MapFeature == MapFeature.None && !base.prefab.Has<PlaceholderObject>())
		{
			ComponentBase.baseLog.WarnFormat(base.prefab, "QuantityObject has no resource: {0}", base.prefab.name);
		}
	}
```


