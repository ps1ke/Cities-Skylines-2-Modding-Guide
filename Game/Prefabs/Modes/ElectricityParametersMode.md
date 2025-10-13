# Game.Prefabs.Modes.ElectricityParametersMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ElectricityParametersMode : Game.Prefabs.Modes.EntityQueryModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Single m_InitialBatteryCharge;
    public UnityEngine.AnimationCurve m_TemperatureConsumptionMultiplier;
    public System.Single m_CloudinessSolarPenalty;

    public ElectricityParametersMode();

    public virtual Unity.Jobs.JobHandle ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps);
    public virtual Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    protected virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public System.Single m_InitialBatteryCharge`  

```csharp
public System.Single m_InitialBatteryCharge;
```

- `public UnityEngine.AnimationCurve m_TemperatureConsumptionMultiplier`  

```csharp
public UnityEngine.AnimationCurve m_TemperatureConsumptionMultiplier;
```

- `public System.Single m_CloudinessSolarPenalty`  

```csharp
public System.Single m_CloudinessSolarPenalty;
```


## Constructors

- `public ElectricityParametersMode()`  

```csharp
public ElectricityParametersMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  

```csharp
public override JobHandle ApplyModeData(EntityManager entityManager, EntityQuery requestedQuery, JobHandle deps)
	{
		Entity singletonEntity = requestedQuery.GetSingletonEntity();
		ElectricityParameterData componentData = entityManager.GetComponentData<ElectricityParameterData>(singletonEntity);
		componentData.m_InitialBatteryCharge = m_InitialBatteryCharge;
		componentData.m_TemperatureConsumptionMultiplier = new AnimationCurve1(m_TemperatureConsumptionMultiplier);
		componentData.m_CloudinessSolarPenalty = m_CloudinessSolarPenalty;
		entityManager.SetComponentData(singletonEntity, componentData);
		return deps;
	}
```

- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public override EntityQueryDesc GetEntityQueryDesc()
	{
		EntityQueryDesc entityQueryDesc = new EntityQueryDesc();
		entityQueryDesc.All = new ComponentType[1] { ComponentType.ReadOnly<ElectricityParameterData>() };
		return entityQueryDesc;
	}
```

- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected override void RecordChanges(EntityManager entityManager, Entity entity)
	{
		entityManager.GetComponentData<ElectricityParameterData>(entity);
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, ref NativeArray<Entity> entities, PrefabSystem prefabSystem)
	{
		Entity entity = entities[0];
		ElectricityParametersPrefab electricityParametersPrefab = prefabSystem.GetPrefab<ElectricityParametersPrefab>(entity);
		ElectricityParameterData componentData = entityManager.GetComponentData<ElectricityParameterData>(entity);
		componentData.m_InitialBatteryCharge = electricityParametersPrefab.m_InitialBatteryCharge;
		componentData.m_TemperatureConsumptionMultiplier = new AnimationCurve1(electricityParametersPrefab.m_TemperatureConsumptionMultiplier);
		componentData.m_CloudinessSolarPenalty = electricityParametersPrefab.m_CloudinessSolarPenalty;
		entityManager.SetComponentData(entity, componentData);
	}
```


