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
public override JobHandle ApplyModeData(EntityManager entityManager, EntityQuery requestedQuery, JobHandle deps)
	{
		Entity singletonEntity = requestedQuery.GetSingletonEntity();
		PollutionParameterData componentData = entityManager.GetComponentData<PollutionParameterData>(singletonEntity);
		componentData.m_GroundMultiplier = m_GroundMultiplier;
		componentData.m_AirMultiplier = m_AirMultiplier;
		componentData.m_NoiseMultiplier = m_NoiseMultiplier;
		componentData.m_NetAirMultiplier = m_NetAirMultiplier;
		componentData.m_NetNoiseMultiplier = m_NetNoiseMultiplier;
		componentData.m_GroundRadius = m_GroundRadius;
		componentData.m_AirRadius = m_AirRadius;
		componentData.m_NoiseRadius = m_NoiseRadius;
		componentData.m_NetNoiseRadius = m_NetNoiseRadius;
		componentData.m_WindAdvectionSpeed = m_WindAdvectionSpeed;
		componentData.m_AirFade = m_AirFade;
		componentData.m_GroundFade = m_GroundFade;
		componentData.m_PlantAirMultiplier = m_PlantAirMultiplier;
		componentData.m_PlantGroundMultiplier = m_PlantGroundMultiplier;
		componentData.m_PlantFade = m_PlantFade;
		componentData.m_FertilityGroundMultiplier = m_FertilityGroundMultiplier;
		componentData.m_DistanceExponent = m_DistanceExponent;
		componentData.m_AirPollutionNotificationLimit = m_AirPollutionNotificationLimit;
		componentData.m_NoisePollutionNotificationLimit = m_NoisePollutionNotificationLimit;
		componentData.m_GroundPollutionNotificationLimit = m_GroundPollutionNotificationLimit;
		componentData.m_AbandonedNoisePollutionMultiplier = m_AbandonedNoisePollutionMultiplier;
		componentData.m_HomelessNoisePollution = m_HomelessNoisePollution;
		componentData.m_GroundPollutionLandValueDivisor = m_GroundPollutionLandValueDivisor;
		entityManager.SetComponentData(singletonEntity, componentData);
		return deps;
	}
```

- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public override EntityQueryDesc GetEntityQueryDesc()
	{
		EntityQueryDesc entityQueryDesc = new EntityQueryDesc();
		entityQueryDesc.All = new ComponentType[1] { ComponentType.ReadOnly<PollutionParameterData>() };
		return entityQueryDesc;
	}
```

- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected override void RecordChanges(EntityManager entityManager, Entity entity)
	{
		entityManager.GetComponentData<PollutionParameterData>(entity);
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, ref NativeArray<Entity> entities, PrefabSystem prefabSystem)
	{
		Entity entity = entities[0];
		PollutionPrefab pollutionPrefab = prefabSystem.GetPrefab<PollutionPrefab>(entity);
		PollutionParameterData componentData = entityManager.GetComponentData<PollutionParameterData>(entity);
		componentData.m_GroundMultiplier = pollutionPrefab.m_GroundMultiplier;
		componentData.m_AirMultiplier = pollutionPrefab.m_AirMultiplier;
		componentData.m_NoiseMultiplier = pollutionPrefab.m_NoiseMultiplier;
		componentData.m_NetAirMultiplier = pollutionPrefab.m_NetAirMultiplier;
		componentData.m_NetNoiseMultiplier = pollutionPrefab.m_NetNoiseMultiplier;
		componentData.m_GroundRadius = pollutionPrefab.m_GroundRadius;
		componentData.m_AirRadius = pollutionPrefab.m_AirRadius;
		componentData.m_NoiseRadius = pollutionPrefab.m_NoiseRadius;
		componentData.m_NetNoiseRadius = pollutionPrefab.m_NetNoiseRadius;
		componentData.m_WindAdvectionSpeed = pollutionPrefab.m_WindAdvectionSpeed;
		componentData.m_AirFade = pollutionPrefab.m_AirFade;
		componentData.m_GroundFade = pollutionPrefab.m_GroundFade;
		componentData.m_PlantAirMultiplier = pollutionPrefab.m_PlantAirMultiplier;
		componentData.m_PlantGroundMultiplier = pollutionPrefab.m_PlantGroundMultiplier;
		componentData.m_PlantFade = pollutionPrefab.m_PlantFade;
		componentData.m_FertilityGroundMultiplier = pollutionPrefab.m_FertilityGroundMultiplier;
		componentData.m_DistanceExponent = pollutionPrefab.m_DistanceExponent;
		componentData.m_AirPollutionNotificationLimit = pollutionPrefab.m_AirPollutionNotificationLimit;
		componentData.m_NoisePollutionNotificationLimit = pollutionPrefab.m_NoisePollutionNotificationLimit;
		componentData.m_GroundPollutionNotificationLimit = pollutionPrefab.m_GroundPollutionNotificationLimit;
		componentData.m_AbandonedNoisePollutionMultiplier = pollutionPrefab.m_AbandonedNoisePollutionMultiplier;
		componentData.m_HomelessNoisePollution = pollutionPrefab.m_HomelessNoisePollution;
		componentData.m_GroundPollutionLandValueDivisor = pollutionPrefab.m_GroundPollutionLandValueDivisor;
		entityManager.SetComponentData(entity, componentData);
	}
```


