# Game.Prefabs.GarbagePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class GarbagePrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.ServicePrefab m_GarbageServicePrefab;
    public Game.Prefabs.NotificationIconPrefab m_GarbageNotificationPrefab;
    public Game.Prefabs.NotificationIconPrefab m_FacilityFullNotificationPrefab;
    public System.Int32 m_HomelessGarbageProduce;
    public System.Int32 m_CollectionGarbageLimit;
    public System.Int32 m_RequestGarbageLimit;
    public System.Int32 m_WarningGarbageLimit;
    public System.Int32 m_MaxGarbageAccumulation;
    public System.Single m_BuildingLevelBalance;
    public System.Single m_EducationBalance;
    public System.Int32 m_HappinessEffectBaseline;
    public System.Int32 m_HappinessEffectStep;

    public System.Boolean ignoreUnlockDependencies { get; }

    public GarbagePrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.ServicePrefab m_GarbageServicePrefab`  

```csharp
public Game.Prefabs.ServicePrefab m_GarbageServicePrefab;
```

- `public Game.Prefabs.NotificationIconPrefab m_GarbageNotificationPrefab`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_GarbageNotificationPrefab;
```

- `public Game.Prefabs.NotificationIconPrefab m_FacilityFullNotificationPrefab`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_FacilityFullNotificationPrefab;
```

- `public System.Int32 m_HomelessGarbageProduce`  

```csharp
public System.Int32 m_HomelessGarbageProduce;
```

- `public System.Int32 m_CollectionGarbageLimit`  

```csharp
public System.Int32 m_CollectionGarbageLimit;
```

- `public System.Int32 m_RequestGarbageLimit`  

```csharp
public System.Int32 m_RequestGarbageLimit;
```

- `public System.Int32 m_WarningGarbageLimit`  

```csharp
public System.Int32 m_WarningGarbageLimit;
```

- `public System.Int32 m_MaxGarbageAccumulation`  

```csharp
public System.Int32 m_MaxGarbageAccumulation;
```

- `public System.Single m_BuildingLevelBalance`  

```csharp
public System.Single m_BuildingLevelBalance;
```

- `public System.Single m_EducationBalance`  

```csharp
public System.Single m_EducationBalance;
```

- `public System.Int32 m_HappinessEffectBaseline`  

```csharp
public System.Int32 m_HappinessEffectBaseline;
```

- `public System.Int32 m_HappinessEffectStep`  

```csharp
public System.Int32 m_HappinessEffectStep;
```


## Properties

- `public System.Boolean ignoreUnlockDependencies { get }`  

```csharp
public System.Boolean ignoreUnlockDependencies { get; }
```


## Constructors

- `public GarbagePrefab()`  

```csharp
public GarbagePrefab();
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


