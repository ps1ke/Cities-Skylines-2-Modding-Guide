# Game.Prefabs.SwimmingAnimal

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class SwimmingAnimal : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Single m_SwimSpeed;
    public Colossal.Mathematics.Bounds1 m_SwimDepth;

    public SwimmingAnimal();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Single m_SwimSpeed`  

```csharp
public System.Single m_SwimSpeed;
```

- `public Colossal.Mathematics.Bounds1 m_SwimDepth`  

```csharp
public Colossal.Mathematics.Bounds1 m_SwimDepth;
```


## Constructors

- `public SwimmingAnimal()`  

```csharp
public SwimmingAnimal();
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
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		AnimalData componentData = entityManager.GetComponentData<AnimalData>(entity);
		componentData.m_SwimSpeed = m_SwimSpeed / 3.6f;
		componentData.m_SwimDepth = m_SwimDepth;
		entityManager.SetComponentData(entity, componentData);
	}
```


