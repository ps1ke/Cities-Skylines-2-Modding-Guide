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


