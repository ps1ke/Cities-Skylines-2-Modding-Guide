# Game.Prefabs.PlaceholderObject

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class PlaceholderObject : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Boolean m_RandomizeGroupIndex;

    public PlaceholderObject();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Boolean m_RandomizeGroupIndex`  

```csharp
public System.Boolean m_RandomizeGroupIndex;
```


## Constructors

- `public PlaceholderObject()`  

```csharp
public PlaceholderObject();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Placeholder>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<PlaceholderObjectElement>());
		components.Add(ComponentType.ReadWrite<PlaceholderObjectData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		if (base.prefab.Has<SpawnableObject>())
		{
			ComponentBase.baseLog.WarnFormat(base.prefab, "PlaceholderObject is SpawnableObject: {0}", base.prefab.name);
		}
		PlaceholderObjectData componentData = new PlaceholderObjectData
		{
			m_RandomizeGroupIndex = m_RandomizeGroupIndex
		};
		entityManager.SetComponentData(entity, componentData);
	}
```


