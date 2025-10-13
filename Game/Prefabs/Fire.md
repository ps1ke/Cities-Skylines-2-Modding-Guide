# Game.Prefabs.Fire

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class Fire : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.EventTargetType m_RandomTargetType;
    public System.Single m_StartProbability;
    public System.Single m_StartIntensity;
    public System.Single m_EscalationRate;
    public System.Single m_SpreadProbability;
    public System.Single m_SpreadRange;

    public Fire();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.EventTargetType m_RandomTargetType`  

```csharp
public Game.Prefabs.EventTargetType m_RandomTargetType;
```

- `public System.Single m_StartProbability`  

```csharp
public System.Single m_StartProbability;
```

- `public System.Single m_StartIntensity`  

```csharp
public System.Single m_StartIntensity;
```

- `public System.Single m_EscalationRate`  

```csharp
public System.Single m_EscalationRate;
```

- `public System.Single m_SpreadProbability`  

```csharp
public System.Single m_SpreadProbability;
```

- `public System.Single m_SpreadRange`  

```csharp
public System.Single m_SpreadRange;
```


## Constructors

- `public Fire()`  

```csharp
public Fire();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Events.Fire>());
		components.Add(ComponentType.ReadWrite<TargetElement>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<FireData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		FireData componentData = default(FireData);
		componentData.m_RandomTargetType = m_RandomTargetType;
		componentData.m_StartProbability = m_StartProbability;
		componentData.m_StartIntensity = m_StartIntensity;
		componentData.m_EscalationRate = m_EscalationRate;
		componentData.m_SpreadProbability = m_SpreadProbability;
		componentData.m_SpreadRange = m_SpreadRange;
		entityManager.SetComponentData(entity, componentData);
	}
```


