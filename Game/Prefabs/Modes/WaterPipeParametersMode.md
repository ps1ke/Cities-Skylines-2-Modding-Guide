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
public override JobHandle ApplyModeData(EntityManager entityManager, EntityQuery requestedQuery, JobHandle deps)
	{
		Entity singletonEntity = requestedQuery.GetSingletonEntity();
		WaterPipeParameterData componentData = entityManager.GetComponentData<WaterPipeParameterData>(singletonEntity);
		componentData.m_GroundwaterReplenish = m_GroundwaterReplenish;
		componentData.m_GroundwaterPurification = m_GroundwaterPurification;
		componentData.m_GroundwaterUsageMultiplier = m_GroundwaterUsageMultiplier;
		componentData.m_GroundwaterPumpEffectiveAmount = m_GroundwaterPumpEffectiveAmount;
		componentData.m_SurfaceWaterUsageMultiplier = m_SurfaceWaterUsageMultiplier;
		componentData.m_SurfaceWaterPumpEffectiveDepth = m_SurfaceWaterPumpEffectiveDepth;
		componentData.m_MaxToleratedPollution = m_MaxToleratedPollution;
		componentData.m_WaterPipePollutionSpreadInterval = m_WaterPipePollutionSpreadInterval;
		componentData.m_StaleWaterPipePurification = m_StaleWaterPipePurification;
		entityManager.SetComponentData(singletonEntity, componentData);
		return deps;
	}
```

- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public override EntityQueryDesc GetEntityQueryDesc()
	{
		EntityQueryDesc entityQueryDesc = new EntityQueryDesc();
		entityQueryDesc.All = new ComponentType[1] { ComponentType.ReadOnly<WaterPipeParameterData>() };
		return entityQueryDesc;
	}
```

- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected override void RecordChanges(EntityManager entityManager, Entity entity)
	{
		entityManager.GetComponentData<WaterPipeParameterData>(entity);
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, ref NativeArray<Entity> entities, PrefabSystem prefabSystem)
	{
		Entity entity = entities[0];
		WaterPipeParametersPrefab waterPipeParametersPrefab = prefabSystem.GetPrefab<WaterPipeParametersPrefab>(entity);
		WaterPipeParameterData componentData = entityManager.GetComponentData<WaterPipeParameterData>(entity);
		componentData.m_GroundwaterReplenish = waterPipeParametersPrefab.m_GroundwaterReplenish;
		componentData.m_GroundwaterPurification = waterPipeParametersPrefab.m_GroundwaterPurification;
		componentData.m_GroundwaterUsageMultiplier = waterPipeParametersPrefab.m_GroundwaterUsageMultiplier;
		componentData.m_GroundwaterPumpEffectiveAmount = waterPipeParametersPrefab.m_GroundwaterPumpEffectiveAmount;
		componentData.m_SurfaceWaterUsageMultiplier = waterPipeParametersPrefab.m_SurfaceWaterUsageMultiplier;
		componentData.m_SurfaceWaterPumpEffectiveDepth = waterPipeParametersPrefab.m_SurfaceWaterPumpEffectiveDepth;
		componentData.m_MaxToleratedPollution = waterPipeParametersPrefab.m_MaxToleratedPollution;
		componentData.m_WaterPipePollutionSpreadInterval = waterPipeParametersPrefab.m_WaterPipePollutionSpreadInterval;
		componentData.m_StaleWaterPipePurification = waterPipeParametersPrefab.m_StaleWaterPipePurification;
		entityManager.SetComponentData(entity, componentData);
	}
```


