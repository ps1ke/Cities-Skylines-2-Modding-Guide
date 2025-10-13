# Game.Prefabs.NetArrow

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class NetArrow : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public UnityEngine.Material m_ArrowMaterial;
    public UnityEngine.Color m_RoadArrowColor;
    public UnityEngine.Color m_TrackArrowColor;

    public NetArrow();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public UnityEngine.Material m_ArrowMaterial`  

```csharp
public UnityEngine.Material m_ArrowMaterial;
```

- `public UnityEngine.Color m_RoadArrowColor`  

```csharp
public UnityEngine.Color m_RoadArrowColor;
```

- `public UnityEngine.Color m_TrackArrowColor`  

```csharp
public UnityEngine.Color m_TrackArrowColor;
```


## Constructors

- `public NetArrow()`  

```csharp
public NetArrow();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<ArrowMaterial>());
		components.Add(ComponentType.ReadWrite<ArrowPosition>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<NetArrowData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		entityManager.SetComponentData(entity, new NetArrowData
		{
			m_RoadColor = m_RoadArrowColor.linear,
			m_TrackColor = m_TrackArrowColor.linear
		});
	}
```


