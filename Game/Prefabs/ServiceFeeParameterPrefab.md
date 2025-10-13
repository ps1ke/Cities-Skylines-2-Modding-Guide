# Game.Prefabs.ServiceFeeParameterPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ServiceFeeParameterPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.FeeParameters m_ElectricityFee;
    public UnityEngine.AnimationCurve m_ElectricityFeeConsumptionMultiplier;
    public Game.Prefabs.FeeParameters m_HealthcareFee;
    public Game.Prefabs.FeeParameters m_BasicEducationFee;
    public Game.Prefabs.FeeParameters m_SecondaryEducationFee;
    public Game.Prefabs.FeeParameters m_HigherEducationFee;
    public Game.Prefabs.FeeParameters m_GarbageFee;
    public Unity.Mathematics.int4 m_GarbageFeeRCIO;
    public Game.Prefabs.FeeParameters m_WaterFee;
    public UnityEngine.AnimationCurve m_WaterFeeConsumptionMultiplier;
    public Game.Prefabs.FeeParameters m_FireResponseFee;
    public Game.Prefabs.FeeParameters m_PoliceFee;

    public ServiceFeeParameterPrefab();

    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
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

- `public Game.Prefabs.FeeParameters m_GarbageFee`  

```csharp
public Game.Prefabs.FeeParameters m_GarbageFee;
```

- `public Unity.Mathematics.int4 m_GarbageFeeRCIO`  

```csharp
public Unity.Mathematics.int4 m_GarbageFeeRCIO;
```

- `public Game.Prefabs.FeeParameters m_WaterFee`  

```csharp
public Game.Prefabs.FeeParameters m_WaterFee;
```

- `public UnityEngine.AnimationCurve m_WaterFeeConsumptionMultiplier`  

```csharp
public UnityEngine.AnimationCurve m_WaterFeeConsumptionMultiplier;
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

- `public ServiceFeeParameterPrefab()`  

```csharp
public ServiceFeeParameterPrefab();
```


## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


