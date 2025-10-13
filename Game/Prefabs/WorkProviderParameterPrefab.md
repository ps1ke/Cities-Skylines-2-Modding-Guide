# Game.Prefabs.WorkProviderParameterPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class WorkProviderParameterPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.NotificationIconPrefab m_UneducatedNotificationPrefab;
    public Game.Prefabs.NotificationIconPrefab m_EducatedNotificationPrefab;
    public System.Int16 m_UneducatedNotificationDelay;
    public System.Int16 m_EducatedNotificationDelay;
    public System.Single m_UneducatedNotificationLimit;
    public System.Single m_EducatedNotificationLimit;
    public System.Int32 m_SeniorEmployeeLevel;

    public WorkProviderParameterPrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.NotificationIconPrefab m_UneducatedNotificationPrefab`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_UneducatedNotificationPrefab;
```

- `public Game.Prefabs.NotificationIconPrefab m_EducatedNotificationPrefab`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_EducatedNotificationPrefab;
```

- `public System.Int16 m_UneducatedNotificationDelay`  

```csharp
public System.Int16 m_UneducatedNotificationDelay;
```

- `public System.Int16 m_EducatedNotificationDelay`  

```csharp
public System.Int16 m_EducatedNotificationDelay;
```

- `public System.Single m_UneducatedNotificationLimit`  

```csharp
public System.Single m_UneducatedNotificationLimit;
```

- `public System.Single m_EducatedNotificationLimit`  

```csharp
public System.Single m_EducatedNotificationLimit;
```

- `public System.Int32 m_SeniorEmployeeLevel`  

```csharp
public System.Int32 m_SeniorEmployeeLevel;
```


## Constructors

- `public WorkProviderParameterPrefab()`  

```csharp
public WorkProviderParameterPrefab();
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


