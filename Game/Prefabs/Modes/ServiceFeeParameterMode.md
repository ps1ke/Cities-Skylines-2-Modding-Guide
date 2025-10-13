# Game.Prefabs.Modes.ServiceFeeParameterMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ServiceFeeParameterMode : Game.Prefabs.Modes.EntityQueryModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.FeeParameters m_ElectricityFee;
    public UnityEngine.AnimationCurve m_ElectricityFeeConsumptionMultiplier;
    public Game.Prefabs.FeeParameters m_HealthcareFee;
    public Game.Prefabs.FeeParameters m_BasicEducationFee;
    public Game.Prefabs.FeeParameters m_SecondaryEducationFee;
    public Game.Prefabs.FeeParameters m_HigherEducationFee;
    public Game.Prefabs.FeeParameters m_WaterFee;
    public UnityEngine.AnimationCurve m_WaterFeeConsumptionMultiplier;
    public Game.Prefabs.FeeParameters m_GarbageFee;
    public Unity.Mathematics.int4 m_GarbageFeeRCIO;
    public Game.Prefabs.FeeParameters m_FireResponseFee;
    public Game.Prefabs.FeeParameters m_PoliceFee;

    public ServiceFeeParameterMode();

    public virtual Unity.Jobs.JobHandle ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps);
    public virtual Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    protected virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public Game.Prefabs.FeeParameters m_ElectricityFee`  

```csharp
public Game.Prefabs.FeeParameters m_ElectricityFee;
```

- `public UnityEngine.AnimationCurve m_ElectricityFeeConsumptionMultiplier`  

```csharp
public UnityEngine.AnimationCurve m_ElectricityFeeConsumptionMultiplier;
```

- `public Game.Prefabs.FeeParameters m_HealthcareFee`  

```csharp
public Game.Prefabs.FeeParameters m_HealthcareFee;
```

- `public Game.Prefabs.FeeParameters m_BasicEducationFee`  

```csharp
public Game.Prefabs.FeeParameters m_BasicEducationFee;
```

- `public Game.Prefabs.FeeParameters m_SecondaryEducationFee`  

```csharp
public Game.Prefabs.FeeParameters m_SecondaryEducationFee;
```

- `public Game.Prefabs.FeeParameters m_HigherEducationFee`  

```csharp
public Game.Prefabs.FeeParameters m_HigherEducationFee;
```

- `public Game.Prefabs.FeeParameters m_WaterFee`  

```csharp
public Game.Prefabs.FeeParameters m_WaterFee;
```

- `public UnityEngine.AnimationCurve m_WaterFeeConsumptionMultiplier`  

```csharp
public UnityEngine.AnimationCurve m_WaterFeeConsumptionMultiplier;
```

- `public Game.Prefabs.FeeParameters m_GarbageFee`  

```csharp
public Game.Prefabs.FeeParameters m_GarbageFee;
```

- `public Unity.Mathematics.int4 m_GarbageFeeRCIO`  

```csharp
public Unity.Mathematics.int4 m_GarbageFeeRCIO;
```

- `public Game.Prefabs.FeeParameters m_FireResponseFee`  

```csharp
public Game.Prefabs.FeeParameters m_FireResponseFee;
```

- `public Game.Prefabs.FeeParameters m_PoliceFee`  

```csharp
public Game.Prefabs.FeeParameters m_PoliceFee;
```


## Constructors

- `public ServiceFeeParameterMode()`  

```csharp
public ServiceFeeParameterMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  

```csharp
public override JobHandle ApplyModeData(EntityManager entityManager, EntityQuery requestedQuery, JobHandle deps)
	{
		Entity singletonEntity = requestedQuery.GetSingletonEntity();
		ServiceFeeParameterData componentData = entityManager.GetComponentData<ServiceFeeParameterData>(singletonEntity);
		componentData.m_ElectricityFee = m_ElectricityFee;
		componentData.m_ElectricityFeeConsumptionMultiplier = new AnimationCurve1(m_ElectricityFeeConsumptionMultiplier);
		componentData.m_HealthcareFee = m_HealthcareFee;
		componentData.m_BasicEducationFee = m_BasicEducationFee;
		componentData.m_SecondaryEducationFee = m_SecondaryEducationFee;
		componentData.m_HigherEducationFee = m_HigherEducationFee;
		componentData.m_WaterFee = m_WaterFee;
		componentData.m_WaterFeeConsumptionMultiplier = new AnimationCurve1(m_WaterFeeConsumptionMultiplier);
		componentData.m_GarbageFee = m_GarbageFee;
		componentData.m_GarbageFeeRCIO = m_GarbageFeeRCIO;
		componentData.m_FireResponseFee = m_FireResponseFee;
		componentData.m_PoliceFee = m_PoliceFee;
		entityManager.SetComponentData(singletonEntity, componentData);
		return deps;
	}
```

- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public override EntityQueryDesc GetEntityQueryDesc()
	{
		EntityQueryDesc entityQueryDesc = new EntityQueryDesc();
		entityQueryDesc.All = new ComponentType[1] { ComponentType.ReadOnly<ServiceFeeParameterData>() };
		return entityQueryDesc;
	}
```

- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected override void RecordChanges(EntityManager entityManager, Entity entity)
	{
		entityManager.GetComponentData<ServiceFeeParameterData>(entity);
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, ref NativeArray<Entity> entities, PrefabSystem prefabSystem)
	{
		Entity entity = entities[0];
		ServiceFeeParameterPrefab serviceFeeParameterPrefab = prefabSystem.GetPrefab<ServiceFeeParameterPrefab>(entity);
		ServiceFeeParameterData componentData = entityManager.GetComponentData<ServiceFeeParameterData>(entity);
		componentData.m_ElectricityFee = serviceFeeParameterPrefab.m_ElectricityFee;
		componentData.m_ElectricityFeeConsumptionMultiplier = new AnimationCurve1(serviceFeeParameterPrefab.m_ElectricityFeeConsumptionMultiplier);
		componentData.m_HealthcareFee = serviceFeeParameterPrefab.m_HealthcareFee;
		componentData.m_BasicEducationFee = serviceFeeParameterPrefab.m_BasicEducationFee;
		componentData.m_SecondaryEducationFee = serviceFeeParameterPrefab.m_SecondaryEducationFee;
		componentData.m_HigherEducationFee = serviceFeeParameterPrefab.m_HigherEducationFee;
		componentData.m_WaterFee = serviceFeeParameterPrefab.m_WaterFee;
		componentData.m_WaterFeeConsumptionMultiplier = new AnimationCurve1(serviceFeeParameterPrefab.m_WaterFeeConsumptionMultiplier);
		componentData.m_GarbageFee = serviceFeeParameterPrefab.m_GarbageFee;
		componentData.m_GarbageFeeRCIO = serviceFeeParameterPrefab.m_GarbageFeeRCIO;
		componentData.m_FireResponseFee = serviceFeeParameterPrefab.m_FireResponseFee;
		componentData.m_PoliceFee = serviceFeeParameterPrefab.m_PoliceFee;
		entityManager.SetComponentData(entity, componentData);
	}
```


