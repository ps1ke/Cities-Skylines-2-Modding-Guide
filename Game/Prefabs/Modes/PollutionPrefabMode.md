# Game.Prefabs.Modes.PollutionPrefabMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class PollutionPrefabMode : Game.Prefabs.Modes.EntityQueryModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Single m_GroundMultiplier;
    public System.Single m_AirMultiplier;
    public System.Single m_NoiseMultiplier;
    public System.Single m_NetAirMultiplier;
    public System.Single m_NetNoiseMultiplier;
    public System.Single m_GroundRadius;
    public System.Single m_AirRadius;
    public System.Single m_NoiseRadius;
    public System.Single m_NetNoiseRadius;
    public System.Single m_WindAdvectionSpeed;
    public System.Int16 m_AirFade;
    public System.Int16 m_GroundFade;
    public System.Single m_PlantAirMultiplier;
    public System.Single m_PlantGroundMultiplier;
    public System.Single m_PlantFade;
    public System.Single m_FertilityGroundMultiplier;
    public System.Single m_DistanceExponent;
    public System.Int32 m_AirPollutionNotificationLimit;
    public System.Int32 m_NoisePollutionNotificationLimit;
    public System.Int32 m_GroundPollutionNotificationLimit;
    public System.Single m_AbandonedNoisePollutionMultiplier;
    public System.Int32 m_HomelessNoisePollution;
    public System.Int32 m_GroundPollutionLandValueDivisor;

    public PollutionPrefabMode();

    public virtual Unity.Jobs.JobHandle ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps);
    public virtual Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    protected virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public System.Single m_GroundMultiplier`  

```csharp
public System.Single m_GroundMultiplier;
```

- `public System.Single m_AirMultiplier`  

```csharp
public System.Single m_AirMultiplier;
```

- `public System.Single m_NoiseMultiplier`  

```csharp
public System.Single m_NoiseMultiplier;
```

- `public System.Single m_NetAirMultiplier`  

```csharp
public System.Single m_NetAirMultiplier;
```

- `public System.Single m_NetNoiseMultiplier`  

```csharp
public System.Single m_NetNoiseMultiplier;
```

- `public System.Single m_GroundRadius`  

```csharp
public System.Single m_GroundRadius;
```

- `public System.Single m_AirRadius`  

```csharp
public System.Single m_AirRadius;
```

- `public System.Single m_NoiseRadius`  

```csharp
public System.Single m_NoiseRadius;
```

- `public System.Single m_NetNoiseRadius`  

```csharp
public System.Single m_NetNoiseRadius;
```

- `public System.Single m_WindAdvectionSpeed`  

```csharp
public System.Single m_WindAdvectionSpeed;
```

- `public System.Int16 m_AirFade`  

```csharp
public System.Int16 m_AirFade;
```

- `public System.Int16 m_GroundFade`  

```csharp
public System.Int16 m_GroundFade;
```

- `public System.Single m_PlantAirMultiplier`  

```csharp
public System.Single m_PlantAirMultiplier;
```

- `public System.Single m_PlantGroundMultiplier`  

```csharp
public System.Single m_PlantGroundMultiplier;
```

- `public System.Single m_PlantFade`  

```csharp
public System.Single m_PlantFade;
```

- `public System.Single m_FertilityGroundMultiplier`  

```csharp
public System.Single m_FertilityGroundMultiplier;
```

- `public System.Single m_DistanceExponent`  

```csharp
public System.Single m_DistanceExponent;
```

- `public System.Int32 m_AirPollutionNotificationLimit`  

```csharp
public System.Int32 m_AirPollutionNotificationLimit;
```

- `public System.Int32 m_NoisePollutionNotificationLimit`  

```csharp
public System.Int32 m_NoisePollutionNotificationLimit;
```

- `public System.Int32 m_GroundPollutionNotificationLimit`  

```csharp
public System.Int32 m_GroundPollutionNotificationLimit;
```

- `public System.Single m_AbandonedNoisePollutionMultiplier`  

```csharp
public System.Single m_AbandonedNoisePollutionMultiplier;
```

- `public System.Int32 m_HomelessNoisePollution`  

```csharp
public System.Int32 m_HomelessNoisePollution;
```

- `public System.Int32 m_GroundPollutionLandValueDivisor`  

```csharp
public System.Int32 m_GroundPollutionLandValueDivisor;
```


## Constructors

- `public PollutionPrefabMode()`  

```csharp
public PollutionPrefabMode();
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


