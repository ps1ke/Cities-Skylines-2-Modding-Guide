# Game.Prefabs.PillarObject

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class PillarObject : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.PillarType m_Type;
    public System.Single m_AnchorOffset;
    public Colossal.Mathematics.Bounds1 m_VerticalPillarOffsetRange;

    public PillarObject();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.PillarType m_Type`  

```csharp
public Game.Prefabs.PillarType m_Type;
```

- `public System.Single m_AnchorOffset`  

```csharp
public System.Single m_AnchorOffset;
```

- `public Colossal.Mathematics.Bounds1 m_VerticalPillarOffsetRange`  

```csharp
public Colossal.Mathematics.Bounds1 m_VerticalPillarOffsetRange;
```


## Constructors

- `public PillarObject()`  

```csharp
public PillarObject();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Pillar>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<PillarData>());
		if (m_AnchorOffset != 0f)
		{
			components.Add(ComponentType.ReadWrite<PlaceableObjectData>());
		}
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		PillarData componentData = default(PillarData);
		componentData.m_Type = m_Type;
		componentData.m_OffsetRange = m_VerticalPillarOffsetRange;
		entityManager.SetComponentData(entity, componentData);
		if (m_AnchorOffset != 0f)
		{
			PlaceableObjectData componentData2 = entityManager.GetComponentData<PlaceableObjectData>(entity);
			componentData2.m_PlacementOffset.y = m_AnchorOffset;
			entityManager.SetComponentData(entity, componentData2);
		}
	}
```


