# Game.Prefabs.Modes.ModeSetting

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ModeSetting : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Boolean m_Enable;
    public Unity.Mathematics.float2 m_ResidentialDemandWeightsSelector;
    public System.Single m_CommercialTaxEffectDemandOffset;
    public System.Single m_IndustrialOfficeTaxEffectDemandOffset;
    public System.Single m_ResourceDemandPerCitizenMultiplier;
    public Unity.Mathematics.float3 m_TaxPaidMultiplier;
    public System.Boolean m_SupportPoorCitizens;
    public System.Int32 m_MinimumWealth;
    public System.Boolean m_EnableGovernmentSubsidies;
    public Unity.Mathematics.int2 m_MoneyCoverThreshold;
    public System.Int32 m_MaxMoneyCoverPercentage;
    public System.Boolean m_EnableAdjustNaturalResources;
    public System.Single m_InitialNaturalResourceBoostMultiplier;
    public System.Int32 m_PercentOreRefillAmountPerDay;
    public System.Int32 m_PercentOilRefillAmountPerDay;
    public System.Collections.Generic.List<Game.Prefabs.Modes.ModePrefab> m_ModePrefabs;
    private System.Collections.Generic.List<Game.Prefabs.Modes.LocalModePrefab> m_LocalModePrefabs;
    private System.Collections.Generic.List<Game.Prefabs.Modes.EntityQueryModePrefab> m_GlobalModePrefabs;

    public ModeSetting();

    public Unity.Jobs.JobHandle ApplyMode(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem, Unity.Jobs.JobHandle deps);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
    public System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
    public System.Void StoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public System.Boolean m_Enable`  

```csharp
public System.Boolean m_Enable;
```

- `public Unity.Mathematics.float2 m_ResidentialDemandWeightsSelector`  

```csharp
public Unity.Mathematics.float2 m_ResidentialDemandWeightsSelector;
```

- `public System.Single m_CommercialTaxEffectDemandOffset`  

```csharp
public System.Single m_CommercialTaxEffectDemandOffset;
```

- `public System.Single m_IndustrialOfficeTaxEffectDemandOffset`  

```csharp
public System.Single m_IndustrialOfficeTaxEffectDemandOffset;
```

- `public System.Single m_ResourceDemandPerCitizenMultiplier`  

```csharp
public System.Single m_ResourceDemandPerCitizenMultiplier;
```

- `public Unity.Mathematics.float3 m_TaxPaidMultiplier`  

```csharp
public Unity.Mathematics.float3 m_TaxPaidMultiplier;
```

- `public System.Boolean m_SupportPoorCitizens`  

```csharp
public System.Boolean m_SupportPoorCitizens;
```

- `public System.Int32 m_MinimumWealth`  

```csharp
public System.Int32 m_MinimumWealth;
```

- `public System.Boolean m_EnableGovernmentSubsidies`  

```csharp
public System.Boolean m_EnableGovernmentSubsidies;
```

- `public Unity.Mathematics.int2 m_MoneyCoverThreshold`  

```csharp
public Unity.Mathematics.int2 m_MoneyCoverThreshold;
```

- `public System.Int32 m_MaxMoneyCoverPercentage`  

```csharp
public System.Int32 m_MaxMoneyCoverPercentage;
```

- `public System.Boolean m_EnableAdjustNaturalResources`  

```csharp
public System.Boolean m_EnableAdjustNaturalResources;
```

- `public System.Single m_InitialNaturalResourceBoostMultiplier`  

```csharp
public System.Single m_InitialNaturalResourceBoostMultiplier;
```

- `public System.Int32 m_PercentOreRefillAmountPerDay`  

```csharp
public System.Int32 m_PercentOreRefillAmountPerDay;
```

- `public System.Int32 m_PercentOilRefillAmountPerDay`  

```csharp
public System.Int32 m_PercentOilRefillAmountPerDay;
```

- `public System.Collections.Generic.List<Game.Prefabs.Modes.ModePrefab> m_ModePrefabs`  

```csharp
public System.Collections.Generic.List<Game.Prefabs.Modes.ModePrefab> m_ModePrefabs;
```

- `private System.Collections.Generic.List<Game.Prefabs.Modes.LocalModePrefab> m_LocalModePrefabs`  

```csharp
private System.Collections.Generic.List<Game.Prefabs.Modes.LocalModePrefab> m_LocalModePrefabs;
```

- `private System.Collections.Generic.List<Game.Prefabs.Modes.EntityQueryModePrefab> m_GlobalModePrefabs`  

```csharp
private System.Collections.Generic.List<Game.Prefabs.Modes.EntityQueryModePrefab> m_GlobalModePrefabs;
```


## Constructors

- `public ModeSetting()`  

```csharp
public ModeSetting();
```


## Methods

- `public ApplyMode(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  

```csharp
public Unity.Jobs.JobHandle ApplyMode(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem, Unity.Jobs.JobHandle deps);
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `public virtual RecordChanges(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
```

- `public RestoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
```

- `public StoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public System.Void StoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
```


