# Game.Prefabs.Modes.WaterPipeParametersMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class WaterPipeParametersMode : Game.Prefabs.Modes.EntityQueryModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Single m_GroundwaterReplenish;
    public System.Int32 m_GroundwaterPurification;
    public System.Single m_GroundwaterUsageMultiplier;
    public System.Single m_GroundwaterPumpEffectiveAmount;
    public System.Single m_SurfaceWaterUsageMultiplier;
    public System.Single m_SurfaceWaterPumpEffectiveDepth;
    public System.Single m_MaxToleratedPollution;
    public System.Int32 m_WaterPipePollutionSpreadInterval;
    public System.Single m_StaleWaterPipePurification;

    public WaterPipeParametersMode();

    public virtual Unity.Jobs.JobHandle ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps);
    public virtual Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    protected virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public System.Single m_GroundwaterReplenish`  

```csharp
public System.Single m_GroundwaterReplenish;
```

- `public System.Int32 m_GroundwaterPurification`  

```csharp
public System.Int32 m_GroundwaterPurification;
```

- `public System.Single m_GroundwaterUsageMultiplier`  

```csharp
public System.Single m_GroundwaterUsageMultiplier;
```

- `public System.Single m_GroundwaterPumpEffectiveAmount`  

```csharp
public System.Single m_GroundwaterPumpEffectiveAmount;
```

- `public System.Single m_SurfaceWaterUsageMultiplier`  

```csharp
public System.Single m_SurfaceWaterUsageMultiplier;
```

- `public System.Single m_SurfaceWaterPumpEffectiveDepth`  

```csharp
public System.Single m_SurfaceWaterPumpEffectiveDepth;
```

- `public System.Single m_MaxToleratedPollution`  

```csharp
public System.Single m_MaxToleratedPollution;
```

- `public System.Int32 m_WaterPipePollutionSpreadInterval`  

```csharp
public System.Int32 m_WaterPipePollutionSpreadInterval;
```

- `public System.Single m_StaleWaterPipePurification`  

```csharp
public System.Single m_StaleWaterPipePurification;
```


## Constructors

- `public WaterPipeParametersMode()`  

```csharp
public WaterPipeParametersMode();
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


