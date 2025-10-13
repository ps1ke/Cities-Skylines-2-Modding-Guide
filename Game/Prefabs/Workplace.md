# Game.Prefabs.Workplace

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `Game.Prefabs.IServiceUpgrade`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class Workplace : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, Game.Prefabs.IServiceUpgrade
{
    public System.Int32 m_Workplaces;
    public System.Int32 m_MinimumWorkersLimit;
    public Game.Prefabs.WorkplaceComplexity m_Complexity;
    public System.Single m_EveningShiftProbability;
    public System.Single m_NightShiftProbability;

    public Workplace();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public System.Void GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Int32 m_Workplaces`  

```csharp
public System.Int32 m_Workplaces;
```

- `public System.Int32 m_MinimumWorkersLimit`  

```csharp
public System.Int32 m_MinimumWorkersLimit;
```

- `public Game.Prefabs.WorkplaceComplexity m_Complexity`  

```csharp
public Game.Prefabs.WorkplaceComplexity m_Complexity;
```

- `public System.Single m_EveningShiftProbability`  

```csharp
public System.Single m_EveningShiftProbability;
```

- `public System.Single m_NightShiftProbability`  

```csharp
public System.Single m_NightShiftProbability;
```


## Constructors

- `public Workplace()`  

```csharp
public Workplace();
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

- `public GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public System.Void GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


