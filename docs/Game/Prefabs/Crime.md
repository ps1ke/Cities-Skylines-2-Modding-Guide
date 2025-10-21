# Game.Prefabs.Crime

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class Crime : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.EventTargetType m_RandomTargetType;
    public Game.Prefabs.CrimeType m_CrimeType;
    public Colossal.Mathematics.Bounds1 m_OccurenceProbability;
    public Colossal.Mathematics.Bounds1 m_RecurrenceProbability;
    public Colossal.Mathematics.Bounds1 m_AlarmDelay;
    public Colossal.Mathematics.Bounds1 m_CrimeDuration;
    public Colossal.Mathematics.Bounds1 m_CrimeIncomeAbsolute;
    public Colossal.Mathematics.Bounds1 m_CrimeIncomeRelative;
    public Colossal.Mathematics.Bounds1 m_JailTimeRange;
    public Colossal.Mathematics.Bounds1 m_PrisonTimeRange;
    public System.Single m_PrisonProbability;

    public Crime();

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

- `public Game.Prefabs.CrimeType m_CrimeType`  

```csharp
public Game.Prefabs.CrimeType m_CrimeType;
```

- `public Colossal.Mathematics.Bounds1 m_OccurenceProbability`  

```csharp
public Colossal.Mathematics.Bounds1 m_OccurenceProbability;
```

- `public Colossal.Mathematics.Bounds1 m_RecurrenceProbability`  

```csharp
public Colossal.Mathematics.Bounds1 m_RecurrenceProbability;
```

- `public Colossal.Mathematics.Bounds1 m_AlarmDelay`  

```csharp
public Colossal.Mathematics.Bounds1 m_AlarmDelay;
```

- `public Colossal.Mathematics.Bounds1 m_CrimeDuration`  

```csharp
public Colossal.Mathematics.Bounds1 m_CrimeDuration;
```

- `public Colossal.Mathematics.Bounds1 m_CrimeIncomeAbsolute`  

```csharp
public Colossal.Mathematics.Bounds1 m_CrimeIncomeAbsolute;
```

- `public Colossal.Mathematics.Bounds1 m_CrimeIncomeRelative`  

```csharp
public Colossal.Mathematics.Bounds1 m_CrimeIncomeRelative;
```

- `public Colossal.Mathematics.Bounds1 m_JailTimeRange`  

```csharp
public Colossal.Mathematics.Bounds1 m_JailTimeRange;
```

- `public Colossal.Mathematics.Bounds1 m_PrisonTimeRange`  

```csharp
public Colossal.Mathematics.Bounds1 m_PrisonTimeRange;
```

- `public System.Single m_PrisonProbability`  

```csharp
public System.Single m_PrisonProbability;
```


## Constructors

- `public Crime()`  

```csharp
public Crime();
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


