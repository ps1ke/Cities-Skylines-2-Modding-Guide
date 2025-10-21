# Game.Prefabs.LandValuePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class LandValuePrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.InfoviewPrefab m_LandValueInfoViewPrefab;
    public System.Single m_LandValueBaseline;
    public System.Single m_HealthCoverageBonusMultiplier;
    public System.Single m_EducationCoverageBonusMultiplier;
    public System.Single m_PoliceCoverageBonusMultiplier;
    public System.Single m_AttractivenessBonusMultiplier;
    public System.Single m_TelecomCoverageBonusMultiplier;
    public System.Single m_CommercialServiceBonusMultiplier;
    public System.Single m_BusBonusMultiplier;
    public System.Single m_TramSubwayBonusMultiplier;
    public System.Int32 m_CommonFactorMaxBonus;
    public System.Single m_GroundPollutionPenaltyMultiplier;
    public System.Single m_AirPollutionPenaltyMultiplier;
    public System.Single m_NoisePollutionPenaltyMultiplier;

    public LandValuePrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.InfoviewPrefab m_LandValueInfoViewPrefab`  

```csharp
public Game.Prefabs.InfoviewPrefab m_LandValueInfoViewPrefab;
```

- `public System.Single m_LandValueBaseline`  

```csharp
public System.Single m_LandValueBaseline;
```

- `public System.Single m_HealthCoverageBonusMultiplier`  

```csharp
public System.Single m_HealthCoverageBonusMultiplier;
```

- `public System.Single m_EducationCoverageBonusMultiplier`  

```csharp
public System.Single m_EducationCoverageBonusMultiplier;
```

- `public System.Single m_PoliceCoverageBonusMultiplier`  

```csharp
public System.Single m_PoliceCoverageBonusMultiplier;
```

- `public System.Single m_AttractivenessBonusMultiplier`  

```csharp
public System.Single m_AttractivenessBonusMultiplier;
```

- `public System.Single m_TelecomCoverageBonusMultiplier`  

```csharp
public System.Single m_TelecomCoverageBonusMultiplier;
```

- `public System.Single m_CommercialServiceBonusMultiplier`  

```csharp
public System.Single m_CommercialServiceBonusMultiplier;
```

- `public System.Single m_BusBonusMultiplier`  

```csharp
public System.Single m_BusBonusMultiplier;
```

- `public System.Single m_TramSubwayBonusMultiplier`  

```csharp
public System.Single m_TramSubwayBonusMultiplier;
```

- `public System.Int32 m_CommonFactorMaxBonus`  

```csharp
public System.Int32 m_CommonFactorMaxBonus;
```

- `public System.Single m_GroundPollutionPenaltyMultiplier`  

```csharp
public System.Single m_GroundPollutionPenaltyMultiplier;
```

- `public System.Single m_AirPollutionPenaltyMultiplier`  

```csharp
public System.Single m_AirPollutionPenaltyMultiplier;
```

- `public System.Single m_NoisePollutionPenaltyMultiplier`  

```csharp
public System.Single m_NoisePollutionPenaltyMultiplier;
```


## Constructors

- `public LandValuePrefab()`  

```csharp
public LandValuePrefab();
```


## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


