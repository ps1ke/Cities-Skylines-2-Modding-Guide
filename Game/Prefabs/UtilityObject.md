# Game.Prefabs.UtilityObject

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class UtilityObject : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Net.UtilityTypes m_UtilityType;
    public Unity.Mathematics.float3 m_UtilityPosition;

    public UtilityObject();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Net.UtilityTypes m_UtilityType`  

```csharp
public Game.Net.UtilityTypes m_UtilityType;
```

- `public Unity.Mathematics.float3 m_UtilityPosition`  

```csharp
public Unity.Mathematics.float3 m_UtilityPosition;
```


## Constructors

- `public UtilityObject()`  

```csharp
public UtilityObject();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Objects.UtilityObject>());
		components.Add(ComponentType.ReadWrite<Color>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<UtilityObjectData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		UtilityObjectData componentData = default(UtilityObjectData);
		componentData.m_UtilityTypes = m_UtilityType;
		componentData.m_UtilityPosition = m_UtilityPosition;
		entityManager.SetComponentData(entity, componentData);
	}
```


