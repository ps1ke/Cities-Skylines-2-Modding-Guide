# Game.Prefabs.JournalEventComponent

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class JournalEventComponent : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.String m_Icon;
    public Game.Events.EventDataTrackingType[] m_TrackedData;
    public Game.Events.EventCityEffectTrackingType[] m_TrackedCityEffects;

    public JournalEventComponent();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public System.Int32 GetDataFlags();
    public System.Int32 GetEffectFlags();
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.String m_Icon`  

```csharp
public System.String m_Icon;
```

- `public Game.Events.EventDataTrackingType[] m_TrackedData`  

```csharp
public Game.Events.EventDataTrackingType[] m_TrackedData;
```

- `public Game.Events.EventCityEffectTrackingType[] m_TrackedCityEffects`  

```csharp
public Game.Events.EventCityEffectTrackingType[] m_TrackedCityEffects;
```


## Constructors

- `public JournalEventComponent()`  

```csharp
public JournalEventComponent();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public GetDataFlags() : System.Int32`  

```csharp
public System.Int32 GetDataFlags();
```

- `public GetEffectFlags() : System.Int32`  

```csharp
public System.Int32 GetEffectFlags();
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


