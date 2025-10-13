# Game.Prefabs.FireEngine

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ExcludeGeneratedModTag`, `ComponentMenu`  

## Code

```csharp
public class FireEngine : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Single m_ExtinguishingRate;
    public System.Single m_ExtinguishingSpread;
    public System.Single m_ExtinguishingCapacity;
    public System.Single m_DestroyedClearDuration;

    public System.Collections.Generic.IEnumerable<System.String> modTags { get; }

    public FireEngine();

    private System.Collections.Generic.IEnumerable<System.String> <>n__0();
    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Single m_ExtinguishingRate`  

```csharp
public System.Single m_ExtinguishingRate;
```

- `public System.Single m_ExtinguishingSpread`  

```csharp
public System.Single m_ExtinguishingSpread;
```

- `public System.Single m_ExtinguishingCapacity`  

```csharp
public System.Single m_ExtinguishingCapacity;
```

- `public System.Single m_DestroyedClearDuration`  

```csharp
public System.Single m_DestroyedClearDuration;
```


## Properties

- `public System.Collections.Generic.IEnumerable<System.String> modTags { get }`  

```csharp
public System.Collections.Generic.IEnumerable<System.String> modTags { get; }
```


## Constructors

- `public FireEngine()`  

```csharp
public FireEngine();
```


## Methods

- `private <>n__0() : System.Collections.Generic.IEnumerable<System.String>`  

```csharp
private System.Collections.Generic.IEnumerable<System.String> <>n__0();
```

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Vehicles.FireEngine>());
		if (components.Contains(ComponentType.ReadWrite<Moving>()))
		{
			components.Add(ComponentType.ReadWrite<PathInformation>());
			components.Add(ComponentType.ReadWrite<ServiceDispatch>());
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<FireEngineData>());
		components.Add(ComponentType.ReadWrite<UpdateFrameData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		entityManager.SetComponentData(entity, new FireEngineData(m_ExtinguishingRate, m_ExtinguishingSpread, m_ExtinguishingCapacity, m_DestroyedClearDuration));
		if (entityManager.HasComponent<CarData>(entity))
		{
			entityManager.SetComponentData(entity, new UpdateFrameData(4));
		}
	}
```


## Nested types

- `Game.Prefabs.FireEngine+<get_modTags>d__8`  

