# Game.Prefabs.AttachedObject

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class AttachedObject : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.AttachedObjectType m_AttachType;
    public System.Single m_AttachOffset;

    public AttachedObject();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.AttachedObjectType m_AttachType`  

```csharp
public Game.Prefabs.AttachedObjectType m_AttachType;
```

- `public System.Single m_AttachOffset`  

```csharp
public System.Single m_AttachOffset;
```


## Constructors

- `public AttachedObject()`  

```csharp
public AttachedObject();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<PlaceableObjectData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		PlaceableObjectData componentData = entityManager.GetComponentData<PlaceableObjectData>(entity);
		switch (m_AttachType)
		{
		case AttachedObjectType.Ground:
			componentData.m_Flags |= PlacementFlags.OnGround;
			componentData.m_PlacementOffset.y = m_AttachOffset;
			break;
		case AttachedObjectType.Wall:
			componentData.m_Flags &= ~PlacementFlags.OnGround;
			componentData.m_Flags |= PlacementFlags.Wall;
			componentData.m_PlacementOffset.z = m_AttachOffset;
			break;
		case AttachedObjectType.Hanging:
			componentData.m_Flags &= ~PlacementFlags.OnGround;
			componentData.m_Flags |= PlacementFlags.Hanging;
			componentData.m_PlacementOffset.y = m_AttachOffset;
			break;
		}
		entityManager.SetComponentData(entity, componentData);
	}
```


