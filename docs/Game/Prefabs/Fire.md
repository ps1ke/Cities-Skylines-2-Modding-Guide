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


