# Game.Prefabs.StatisticTriggerPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class StatisticTriggerPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.StatisticTriggerType m_Type;
    public Game.Prefabs.StatisticsPrefab m_StatisticPrefab;
    public System.Int32 m_StatisticParameter;
    public Game.Prefabs.StatisticsPrefab m_NormalizeWithPrefab;
    public System.Int32 m_NormalizeWithParameter;
    public System.Int32 m_TimeFrame;
    public System.Int32 m_MinSamples;

    public StatisticTriggerPrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.StatisticTriggerType m_Type`  

```csharp
public Game.Prefabs.StatisticTriggerType m_Type;
```

- `public Game.Prefabs.StatisticsPrefab m_StatisticPrefab`  

```csharp
public Game.Prefabs.StatisticsPrefab m_StatisticPrefab;
```

- `public System.Int32 m_StatisticParameter`  

```csharp
public System.Int32 m_StatisticParameter;
```

- `public Game.Prefabs.StatisticsPrefab m_NormalizeWithPrefab`  

```csharp
public Game.Prefabs.StatisticsPrefab m_NormalizeWithPrefab;
```

- `public System.Int32 m_NormalizeWithParameter`  

```csharp
public System.Int32 m_NormalizeWithParameter;
```

- `public System.Int32 m_TimeFrame`  

```csharp
public System.Int32 m_TimeFrame;
```

- `public System.Int32 m_MinSamples`  

```csharp
public System.Int32 m_MinSamples;
```


## Constructors

- `public StatisticTriggerPrefab()`  

```csharp
public StatisticTriggerPrefab();
```


## Methods

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


