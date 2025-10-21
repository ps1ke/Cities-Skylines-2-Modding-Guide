# Game.Prefabs.HealthcarePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class HealthcarePrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.PrefabBase m_HealthcareServicePrefab;
    public Game.Prefabs.NotificationIconPrefab m_AmbulanceNotificationPrefab;
    public Game.Prefabs.NotificationIconPrefab m_HearseNotificationPrefab;
    public Game.Prefabs.NotificationIconPrefab m_FacilityFullNotificationPrefab;
    public System.Single m_TransportWarningTime;
    public System.Single m_NoResourceTreatmentPenalty;
    public System.Single m_BuildingDestoryDeathRate;
    public UnityEngine.AnimationCurve m_DeathRate;

    public HealthcarePrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.PrefabBase m_HealthcareServicePrefab`  

```csharp
public Game.Prefabs.PrefabBase m_HealthcareServicePrefab;
```

- `public Game.Prefabs.NotificationIconPrefab m_AmbulanceNotificationPrefab`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_AmbulanceNotificationPrefab;
```

- `public Game.Prefabs.NotificationIconPrefab m_HearseNotificationPrefab`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_HearseNotificationPrefab;
```

- `public Game.Prefabs.NotificationIconPrefab m_FacilityFullNotificationPrefab`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_FacilityFullNotificationPrefab;
```

- `public System.Single m_TransportWarningTime`  

```csharp
public System.Single m_TransportWarningTime;
```

- `public System.Single m_NoResourceTreatmentPenalty`  

```csharp
public System.Single m_NoResourceTreatmentPenalty;
```

- `public System.Single m_BuildingDestoryDeathRate`  

```csharp
public System.Single m_BuildingDestoryDeathRate;
```

- `public UnityEngine.AnimationCurve m_DeathRate`  

```csharp
public UnityEngine.AnimationCurve m_DeathRate;
```


## Constructors

- `public HealthcarePrefab()`  

```csharp
public HealthcarePrefab();
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


