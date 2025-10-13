# Game.Prefabs.OutsideTradeParameterPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class OutsideTradeParameterPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Single m_ElectricityImportPrice;
    public System.Single m_ElectricityExportPrice;
    public System.Single m_WaterImportPrice;
    public System.Single m_WaterExportPrice;
    public System.Single m_WaterExportPollutionTolerance;
    public System.Single m_SewageExportPrice;
    public System.Single m_AirWeightMultiplier;
    public System.Single m_RoadWeightMultiplier;
    public System.Single m_TrainWeightMultiplier;
    public System.Single m_ShipWeightMultiplier;
    public System.Single m_AirDistanceMultiplier;
    public System.Single m_RoadDistanceMultiplier;
    public System.Single m_TrainDistanceMultiplier;
    public System.Single m_ShipDistanceMultiplier;
    public System.Single m_AmbulanceImportServiceFee;
    public System.Single m_HearseImportServiceFee;
    public System.Single m_FireEngineImportServiceFee;
    public System.Single m_GarbageImportServiceFee;
    public System.Single m_PoliceImportServiceFee;
    public System.Int32 m_OCServiceTradePopulationRange;

    public OutsideTradeParameterPrefab();

    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
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

- `public System.Single m_AirWeightMultiplier`  

```csharp
public System.Single m_AirWeightMultiplier;
```

- `public System.Single m_RoadWeightMultiplier`  

```csharp
public System.Single m_RoadWeightMultiplier;
```

- `public System.Single m_TrainWeightMultiplier`  

```csharp
public System.Single m_TrainWeightMultiplier;
```

- `public System.Single m_ShipWeightMultiplier`  

```csharp
public System.Single m_ShipWeightMultiplier;
```

- `public System.Single m_AirDistanceMultiplier`  

```csharp
public System.Single m_AirDistanceMultiplier;
```

- `public System.Single m_RoadDistanceMultiplier`  

```csharp
public System.Single m_RoadDistanceMultiplier;
```

- `public System.Single m_TrainDistanceMultiplier`  

```csharp
public System.Single m_TrainDistanceMultiplier;
```

- `public System.Single m_ShipDistanceMultiplier`  

```csharp
public System.Single m_ShipDistanceMultiplier;
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

- `public OutsideTradeParameterPrefab()`  

```csharp
public OutsideTradeParameterPrefab();
```


## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<OutsideTradeParameterData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		entityManager.SetComponentData(entity, new OutsideTradeParameterData
		{
			m_ElectricityImportPrice = m_ElectricityImportPrice,
			m_ElectricityExportPrice = m_ElectricityExportPrice,
			m_WaterImportPrice = m_WaterImportPrice,
			m_WaterExportPrice = m_WaterExportPrice,
			m_WaterExportPollutionTolerance = m_WaterExportPollutionTolerance,
			m_SewageExportPrice = m_SewageExportPrice,
			m_AirDistanceMultiplier = m_AirDistanceMultiplier,
			m_RoadDistanceMultiplier = m_RoadDistanceMultiplier,
			m_TrainDistanceMultiplier = m_TrainDistanceMultiplier,
			m_ShipDistanceMultiplier = m_ShipDistanceMultiplier,
			m_AirWeightMultiplier = m_AirWeightMultiplier,
			m_RoadWeightMultiplier = m_RoadWeightMultiplier,
			m_TrainWeightMultiplier = m_TrainWeightMultiplier,
			m_ShipWeightMultiplier = m_ShipWeightMultiplier,
			m_AmbulanceImportServiceFee = m_AmbulanceImportServiceFee,
			m_HearseImportServiceFee = m_HearseImportServiceFee,
			m_FireEngineImportServiceFee = m_FireEngineImportServiceFee,
			m_GarbageImportServiceFee = m_GarbageImportServiceFee,
			m_PoliceImportServiceFee = m_PoliceImportServiceFee,
			m_OCServiceTradePopulationRange = m_OCServiceTradePopulationRange
		});
	}
```


