# Game.Prefabs.CalendarEvent

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class CalendarEvent : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.EventTargetType m_RandomTargetType;
    public Colossal.Mathematics.Bounds1 m_AffectedProbability;
    public Colossal.Mathematics.Bounds1 m_OccurenceProbability;
    public Game.Prefabs.CalendarEventMonths m_AllowedMonths;
    public Game.Prefabs.CalendarEventTimes m_AllowedTimes;
    public System.Int32 m_Duration;

    public CalendarEvent();

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

- `public Colossal.Mathematics.Bounds1 m_AffectedProbability`  

```csharp
public Colossal.Mathematics.Bounds1 m_AffectedProbability;
```

- `public Colossal.Mathematics.Bounds1 m_OccurenceProbability`  

```csharp
public Colossal.Mathematics.Bounds1 m_OccurenceProbability;
```

- `public Game.Prefabs.CalendarEventMonths m_AllowedMonths`  

```csharp
public Game.Prefabs.CalendarEventMonths m_AllowedMonths;
```

- `public Game.Prefabs.CalendarEventTimes m_AllowedTimes`  

```csharp
public Game.Prefabs.CalendarEventTimes m_AllowedTimes;
```

- `public System.Int32 m_Duration`  

```csharp
public System.Int32 m_Duration;
```


## Constructors

- `public CalendarEvent()`  

```csharp
public CalendarEvent();
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


