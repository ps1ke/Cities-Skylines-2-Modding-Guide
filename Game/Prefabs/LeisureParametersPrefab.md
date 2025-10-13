# Game.Prefabs.LeisureParametersPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class LeisureParametersPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.EventPrefab m_TravelingEvent;
    public Game.Prefabs.EventPrefab m_AttractionPrefab;
    public Game.Prefabs.EventPrefab m_SightseeingPrefab;
    public System.Int32 m_LeisureRandomFactor;
    public System.Int32 m_TouristLodgingConsumePerDay;
    public System.Int32 m_TouristServiceConsumePerDay;

    public LeisureParametersPrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.EventPrefab m_TravelingEvent`  

```csharp
public Game.Prefabs.EventPrefab m_TravelingEvent;
```

- `public Game.Prefabs.EventPrefab m_AttractionPrefab`  

```csharp
public Game.Prefabs.EventPrefab m_AttractionPrefab;
```

- `public Game.Prefabs.EventPrefab m_SightseeingPrefab`  

```csharp
public Game.Prefabs.EventPrefab m_SightseeingPrefab;
```

- `public System.Int32 m_LeisureRandomFactor`  

```csharp
public System.Int32 m_LeisureRandomFactor;
```

- `public System.Int32 m_TouristLodgingConsumePerDay`  

```csharp
public System.Int32 m_TouristLodgingConsumePerDay;
```

- `public System.Int32 m_TouristServiceConsumePerDay`  

```csharp
public System.Int32 m_TouristServiceConsumePerDay;
```


## Constructors

- `public LeisureParametersPrefab()`  

```csharp
public LeisureParametersPrefab();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


