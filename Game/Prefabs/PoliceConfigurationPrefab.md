# Game.Prefabs.PoliceConfigurationPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class PoliceConfigurationPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.PrefabBase m_PoliceServicePrefab;
    public Game.Prefabs.NotificationIconPrefab m_TrafficAccidentNotificationPrefab;
    public Game.Prefabs.NotificationIconPrefab m_CrimeSceneNotificationPrefab;
    public System.Single m_MaxCrimeAccumulation;
    public System.Single m_CrimeAccumulationTolerance;
    public System.Int32 m_HomeCrimeEffect;
    public System.Int32 m_WorkplaceCrimeEffect;
    public System.Single m_WelfareCrimeRecurrenceFactor;
    public System.Single m_CrimePoliceCoverageFactor;
    public System.Single m_CrimePopulationReduction;

    public System.Boolean ignoreUnlockDependencies { get; }

    public PoliceConfigurationPrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.PrefabBase m_PoliceServicePrefab`  

```csharp
public Game.Prefabs.PrefabBase m_PoliceServicePrefab;
```

- `public Game.Prefabs.NotificationIconPrefab m_TrafficAccidentNotificationPrefab`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_TrafficAccidentNotificationPrefab;
```

- `public Game.Prefabs.NotificationIconPrefab m_CrimeSceneNotificationPrefab`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_CrimeSceneNotificationPrefab;
```

- `public System.Single m_MaxCrimeAccumulation`  

```csharp
public System.Single m_MaxCrimeAccumulation;
```

- `public System.Single m_CrimeAccumulationTolerance`  

```csharp
public System.Single m_CrimeAccumulationTolerance;
```

- `public System.Int32 m_HomeCrimeEffect`  

```csharp
public System.Int32 m_HomeCrimeEffect;
```

- `public System.Int32 m_WorkplaceCrimeEffect`  

```csharp
public System.Int32 m_WorkplaceCrimeEffect;
```

- `public System.Single m_WelfareCrimeRecurrenceFactor`  

```csharp
public System.Single m_WelfareCrimeRecurrenceFactor;
```

- `public System.Single m_CrimePoliceCoverageFactor`  

```csharp
public System.Single m_CrimePoliceCoverageFactor;
```

- `public System.Single m_CrimePopulationReduction`  

```csharp
public System.Single m_CrimePopulationReduction;
```


## Properties

- `public System.Boolean ignoreUnlockDependencies { get }`  

```csharp
public System.Boolean ignoreUnlockDependencies { get; }
```


## Constructors

- `public PoliceConfigurationPrefab()`  

```csharp
public PoliceConfigurationPrefab();
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


