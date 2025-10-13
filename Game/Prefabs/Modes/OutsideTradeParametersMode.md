# Game.Prefabs.Modes.OutsideTradeParametersMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class OutsideTradeParametersMode : Game.Prefabs.Modes.EntityQueryModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Single m_ElectricityImportPrice;
    public System.Single m_ElectricityExportPrice;
    public System.Single m_WaterImportPrice;
    public System.Single m_WaterExportPrice;
    public System.Single m_WaterExportPollutionTolerance;
    public System.Single m_SewageExportPrice;
    public System.Single m_AirWeightMultiplierOverridden;
    public System.Single m_RoadWeightMultiplierOverridden;
    public System.Single m_TrainWeightMultiplierOverridden;
    public System.Single m_ShipWeightMultiplierOverridden;
    public System.Single m_AirDistanceMultiplierOverridden;
    public System.Single m_RoadDistanceMultiplierOverridden;
    public System.Single m_TrainDistanceMultiplierOverridden;
    public System.Single m_ShipDistanceMultiplierOverridden;
    public System.Single m_AmbulanceImportServiceFee;
    public System.Single m_HearseImportServiceFee;
    public System.Single m_FireEngineImportServiceFee;
    public System.Single m_GarbageImportServiceFee;
    public System.Single m_PoliceImportServiceFee;
    public System.Int32 m_OCServiceTradePopulationRange;

    public OutsideTradeParametersMode();

    public virtual Unity.Jobs.JobHandle ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps);
    public virtual Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    protected virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public System.Single m_ElectricityImportPrice`  

```csharp
public System.Single m_ElectricityImportPrice;
```

- `public System.Single m_ElectricityExportPrice`  

```csharp
public System.Single m_ElectricityExportPrice;
```

- `public System.Single m_WaterImportPrice`  

```csharp
public System.Single m_WaterImportPrice;
```

- `public System.Single m_WaterExportPrice`  

```csharp
public System.Single m_WaterExportPrice;
```

- `public System.Single m_WaterExportPollutionTolerance`  

```csharp
public System.Single m_WaterExportPollutionTolerance;
```

- `public System.Single m_SewageExportPrice`  

```csharp
public System.Single m_SewageExportPrice;
```

- `public System.Single m_AirWeightMultiplierOverridden`  

```csharp
public System.Single m_AirWeightMultiplierOverridden;
```

- `public System.Single m_RoadWeightMultiplierOverridden`  

```csharp
public System.Single m_RoadWeightMultiplierOverridden;
```

- `public System.Single m_TrainWeightMultiplierOverridden`  

```csharp
public System.Single m_TrainWeightMultiplierOverridden;
```

- `public System.Single m_ShipWeightMultiplierOverridden`  

```csharp
public System.Single m_ShipWeightMultiplierOverridden;
```

- `public System.Single m_AirDistanceMultiplierOverridden`  

```csharp
public System.Single m_AirDistanceMultiplierOverridden;
```

- `public System.Single m_RoadDistanceMultiplierOverridden`  

```csharp
public System.Single m_RoadDistanceMultiplierOverridden;
```

- `public System.Single m_TrainDistanceMultiplierOverridden`  

```csharp
public System.Single m_TrainDistanceMultiplierOverridden;
```

- `public System.Single m_ShipDistanceMultiplierOverridden`  

```csharp
public System.Single m_ShipDistanceMultiplierOverridden;
```

- `public System.Single m_AmbulanceImportServiceFee`  

```csharp
public System.Single m_AmbulanceImportServiceFee;
```

- `public System.Single m_HearseImportServiceFee`  

```csharp
public System.Single m_HearseImportServiceFee;
```

- `public System.Single m_FireEngineImportServiceFee`  

```csharp
public System.Single m_FireEngineImportServiceFee;
```

- `public System.Single m_GarbageImportServiceFee`  

```csharp
public System.Single m_GarbageImportServiceFee;
```

- `public System.Single m_PoliceImportServiceFee`  

```csharp
public System.Single m_PoliceImportServiceFee;
```

- `public System.Int32 m_OCServiceTradePopulationRange`  

```csharp
public System.Int32 m_OCServiceTradePopulationRange;
```


## Constructors

- `public OutsideTradeParametersMode()`  

```csharp
public OutsideTradeParametersMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  

```csharp
public override JobHandle ApplyModeData(EntityManager entityManager, EntityQuery requestedQuery, JobHandle deps)
	{
		Entity singletonEntity = requestedQuery.GetSingletonEntity();
		OutsideTradeParameterData componentData = entityManager.GetComponentData<OutsideTradeParameterData>(singletonEntity);
		componentData.m_ElectricityImportPrice = m_ElectricityImportPrice;
		componentData.m_ElectricityExportPrice = m_ElectricityExportPrice;
		componentData.m_WaterImportPrice = m_WaterImportPrice;
		componentData.m_WaterExportPrice = m_WaterExportPrice;
		componentData.m_WaterExportPollutionTolerance = m_WaterExportPollutionTolerance;
		componentData.m_SewageExportPrice = m_SewageExportPrice;
		componentData.m_AirWeightMultiplier = m_AirWeightMultiplierOverridden;
		componentData.m_RoadWeightMultiplier = m_RoadWeightMultiplierOverridden;
		componentData.m_TrainWeightMultiplier = m_TrainWeightMultiplierOverridden;
		componentData.m_ShipWeightMultiplier = m_ShipWeightMultiplierOverridden;
		componentData.m_AirDistanceMultiplier = m_AirDistanceMultiplierOverridden;
		componentData.m_RoadDistanceMultiplier = m_RoadDistanceMultiplierOverridden;
		componentData.m_TrainDistanceMultiplier = m_TrainDistanceMultiplierOverridden;
		componentData.m_ShipDistanceMultiplier = m_ShipDistanceMultiplierOverridden;
		componentData.m_AmbulanceImportServiceFee = m_AmbulanceImportServiceFee;
		componentData.m_HearseImportServiceFee = m_HearseImportServiceFee;
		componentData.m_FireEngineImportServiceFee = m_FireEngineImportServiceFee;
		componentData.m_GarbageImportServiceFee = m_GarbageImportServiceFee;
		componentData.m_PoliceImportServiceFee = m_PoliceImportServiceFee;
		componentData.m_OCServiceTradePopulationRange = m_OCServiceTradePopulationRange;
		entityManager.SetComponentData(singletonEntity, componentData);
		return deps;
	}
```

- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public override EntityQueryDesc GetEntityQueryDesc()
	{
		EntityQueryDesc entityQueryDesc = new EntityQueryDesc();
		entityQueryDesc.All = new ComponentType[1] { ComponentType.ReadOnly<OutsideTradeParameterData>() };
		return entityQueryDesc;
	}
```

- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected override void RecordChanges(EntityManager entityManager, Entity entity)
	{
		entityManager.GetComponentData<OutsideTradeParameterData>(entity);
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, ref NativeArray<Entity> entities, PrefabSystem prefabSystem)
	{
		Entity entity = entities[0];
		OutsideTradeParameterPrefab outsideTradeParameterPrefab = prefabSystem.GetPrefab<OutsideTradeParameterPrefab>(entity);
		OutsideTradeParameterData componentData = entityManager.GetComponentData<OutsideTradeParameterData>(entity);
		componentData.m_ElectricityImportPrice = outsideTradeParameterPrefab.m_ElectricityImportPrice;
		componentData.m_ElectricityExportPrice = outsideTradeParameterPrefab.m_ElectricityExportPrice;
		componentData.m_WaterImportPrice = outsideTradeParameterPrefab.m_WaterImportPrice;
		componentData.m_WaterExportPrice = outsideTradeParameterPrefab.m_WaterExportPrice;
		componentData.m_WaterExportPollutionTolerance = outsideTradeParameterPrefab.m_WaterExportPollutionTolerance;
		componentData.m_SewageExportPrice = outsideTradeParameterPrefab.m_SewageExportPrice;
		componentData.m_AirWeightMultiplier = outsideTradeParameterPrefab.m_AirWeightMultiplier;
		componentData.m_RoadWeightMultiplier = outsideTradeParameterPrefab.m_RoadWeightMultiplier;
		componentData.m_TrainWeightMultiplier = outsideTradeParameterPrefab.m_TrainWeightMultiplier;
		componentData.m_ShipWeightMultiplier = outsideTradeParameterPrefab.m_ShipWeightMultiplier;
		componentData.m_AirDistanceMultiplier = outsideTradeParameterPrefab.m_AirDistanceMultiplier;
		componentData.m_RoadDistanceMultiplier = outsideTradeParameterPrefab.m_RoadDistanceMultiplier;
		componentData.m_TrainDistanceMultiplier = outsideTradeParameterPrefab.m_TrainDistanceMultiplier;
		componentData.m_ShipDistanceMultiplier = outsideTradeParameterPrefab.m_ShipDistanceMultiplier;
		componentData.m_AmbulanceImportServiceFee = outsideTradeParameterPrefab.m_AmbulanceImportServiceFee;
		componentData.m_HearseImportServiceFee = outsideTradeParameterPrefab.m_HearseImportServiceFee;
		componentData.m_FireEngineImportServiceFee = outsideTradeParameterPrefab.m_FireEngineImportServiceFee;
		componentData.m_GarbageImportServiceFee = outsideTradeParameterPrefab.m_GarbageImportServiceFee;
		componentData.m_PoliceImportServiceFee = outsideTradeParameterPrefab.m_PoliceImportServiceFee;
		componentData.m_OCServiceTradePopulationRange = outsideTradeParameterPrefab.m_OCServiceTradePopulationRange;
		entityManager.SetComponentData(entity, componentData);
	}
```


