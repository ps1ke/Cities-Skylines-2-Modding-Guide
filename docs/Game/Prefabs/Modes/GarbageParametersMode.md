# Game.Prefabs.Modes.GarbageParametersMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class GarbageParametersMode : Game.Prefabs.Modes.EntityQueryModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Int32 m_HomelessGarbageProduce;
    public System.Int32 m_CollectionGarbageLimit;
    public System.Int32 m_RequestGarbageLimit;
    public System.Int32 m_WarningGarbageLimit;
    public System.Int32 m_MaxGarbageAccumulation;
    public System.Single m_BuildingLevelBalance;
    public System.Single m_EducationBalance;
    public System.Int32 m_HappinessEffectBaseline;
    public System.Int32 m_HappinessEffectStep;

    public GarbageParametersMode();

    public virtual Unity.Jobs.JobHandle ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps);
    public virtual Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    protected virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

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


## Constructors

- `public GarbageParametersMode()`  

```csharp
public GarbageParametersMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  

```csharp
public virtual Unity.Jobs.JobHandle ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps);
```

- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public virtual Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
```

- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
```


