# Game.Prefabs.FloatingObject

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class FloatingObject : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Single m_FloatingOffset;
    public System.Boolean m_FixedToBottom;
    public System.Boolean m_AllowDryland;

    public FloatingObject();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Single m_FloatingOffset`  

```csharp
public System.Single m_FloatingOffset;
```

- `public System.Boolean m_FixedToBottom`  

```csharp
public System.Boolean m_FixedToBottom;
```

- `public System.Boolean m_AllowDryland`  

```csharp
public System.Boolean m_AllowDryland;
```


## Constructors

- `public FloatingObject()`  

```csharp
public FloatingObject();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		if (!m_FixedToBottom && base.prefab is StaticObjectPrefab)
		{
			components.Add(ComponentType.ReadWrite<Swaying>());
			components.Add(ComponentType.ReadWrite<InterpolatedTransform>());
		}
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
		componentData.m_PlacementOffset.y = m_FloatingOffset;
		if (m_AllowDryland)
		{
			componentData.m_Flags |= PlacementFlags.OnGround | PlacementFlags.Floating;
		}
		else
		{
			componentData.m_Flags &= ~PlacementFlags.OnGround;
			componentData.m_Flags |= PlacementFlags.Floating;
		}
		if (!m_FixedToBottom)
		{
			componentData.m_Flags |= PlacementFlags.Swaying;
		}
		entityManager.SetComponentData(entity, componentData);
	}
```


