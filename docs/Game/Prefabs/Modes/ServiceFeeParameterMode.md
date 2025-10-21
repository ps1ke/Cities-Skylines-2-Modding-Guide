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


