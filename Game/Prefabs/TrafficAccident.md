# Game.Prefabs.TrafficAccident

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TrafficAccident : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.EventTargetType m_RandomSiteType;
    public Game.Prefabs.EventTargetType m_SubjectType;
    public Game.Prefabs.TrafficAccidentType m_AccidentType;
    public System.Single m_OccurrenceProbability;

    public TrafficAccident();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.EventTargetType m_RandomSiteType`  

```csharp
public Game.Prefabs.EventTargetType m_RandomSiteType;
```

- `public Game.Prefabs.EventTargetType m_SubjectType`  

```csharp
public Game.Prefabs.EventTargetType m_SubjectType;
```

- `public Game.Prefabs.TrafficAccidentType m_AccidentType`  

```csharp
public Game.Prefabs.TrafficAccidentType m_AccidentType;
```

- `public System.Single m_OccurrenceProbability`  

```csharp
public System.Single m_OccurrenceProbability;
```


## Constructors

- `public TrafficAccident()`  

```csharp
public TrafficAccident();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


