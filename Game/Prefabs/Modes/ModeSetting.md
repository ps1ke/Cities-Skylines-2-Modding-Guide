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
public JobHandle ApplyMode(EntityManager entityManager, PrefabSystem prefabSystem, JobHandle deps)
	{
		Entity singletonEntity = entityManager.CreateEntityQuery(ComponentType.ReadOnly<ModeSettingData>()).GetSingletonEntity();
		ModeSettingData componentData = new ModeSettingData
		{
			m_Enable = m_Enable,
			m_ResidentialDemandWeightsSelector = m_ResidentialDemandWeightsSelector,
			m_CommercialTaxEffectDemandOffset = m_CommercialTaxEffectDemandOffset,
			m_IndustrialOfficeTaxEffectDemandOffset = m_IndustrialOfficeTaxEffectDemandOffset,
			m_ResourceDemandPerCitizenMultiplier = m_ResourceDemandPerCitizenMultiplier,
			m_TaxPaidMultiplier = m_TaxPaidMultiplier,
			m_SupportPoorCitizens = m_SupportPoorCitizens,
			m_MinimumWealth = m_MinimumWealth,
			m_EnableGovernmentSubsidies = m_EnableGovernmentSubsidies,
			m_MoneyCoverThreshold = m_MoneyCoverThreshold,
			m_MaxMoneyCoverPercentage = m_MaxMoneyCoverPercentage,
			m_EnableAdjustNaturalResources = m_EnableAdjustNaturalResources,
			m_InitialNaturalResourceBoostMultiplier = m_InitialNaturalResourceBoostMultiplier,
			m_PercentOreRefillAmountPerDay = m_PercentOreRefillAmountPerDay,
			m_PercentOilRefillAmountPerDay = m_PercentOilRefillAmountPerDay
		};
		entityManager.SetComponentData(singletonEntity, componentData);
		for (int i = 0; i < m_LocalModePrefabs.Count; i++)
		{
			m_LocalModePrefabs[i].ApplyModeData(entityManager, prefabSystem);
		}
		for (int j = 0; j < m_GlobalModePrefabs.Count; j++)
		{
			EntityQuery requestedQuery = entityManager.CreateEntityQuery(m_GlobalModePrefabs[j].GetEntityQueryDesc());
			if (!requestedQuery.IsEmptyIgnoreFilter)
			{
				deps = m_GlobalModePrefabs[j].ApplyModeData(entityManager, requestedQuery, deps);
			}
		}
		return deps;
	}
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		if (m_ModePrefabs != null)
		{
			for (int i = 0; i < m_ModePrefabs.Count; i++)
			{
				prefabs.Add(m_ModePrefabs[i]);
			}
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<GameModeSettingData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		m_LocalModePrefabs = new List<LocalModePrefab>();
		m_GlobalModePrefabs = new List<EntityQueryModePrefab>();
		if (m_ModePrefabs == null)
		{
			return;
		}
		for (int i = 0; i < m_ModePrefabs.Count; i++)
		{
			if (m_ModePrefabs[i] is LocalModePrefab item)
			{
				m_LocalModePrefabs.Add(item);
			}
			else if (m_ModePrefabs[i] is EntityQueryModePrefab item2)
			{
				m_GlobalModePrefabs.Add(item2);
			}
		}
	}
```

- `public virtual RecordChanges(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public virtual void RecordChanges(EntityManager entityManager, PrefabSystem prefabSystem)
	{
		for (int i = 0; i < m_LocalModePrefabs.Count; i++)
		{
		}
		for (int j = 0; j < m_GlobalModePrefabs.Count; j++)
		{
			entityManager.CreateEntityQuery(m_GlobalModePrefabs[j].GetEntityQueryDesc()).ToEntityArray(Allocator.TempJob).Dispose();
		}
	}
```

- `public RestoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public void RestoreDefaultData(EntityManager entityManager, PrefabSystem prefabSystem)
	{
		Entity singletonEntity = entityManager.CreateEntityQuery(ComponentType.ReadOnly<ModeSettingData>()).GetSingletonEntity();
		entityManager.SetComponentData(singletonEntity, new ModeSettingData
		{
			m_Enable = false
		});
		for (int i = 0; i < m_LocalModePrefabs.Count; i++)
		{
			m_LocalModePrefabs[i].RestoreDefaultData(entityManager, prefabSystem);
		}
		for (int j = 0; j < m_GlobalModePrefabs.Count; j++)
		{
			EntityQuery entityQuery = entityManager.CreateEntityQuery(m_GlobalModePrefabs[j].GetEntityQueryDesc());
			if (!entityQuery.IsEmptyIgnoreFilter)
			{
				NativeArray<Entity> entities = entityQuery.ToEntityArray(Allocator.TempJob);
				m_GlobalModePrefabs[j].RestoreDefaultData(entityManager, ref entities, prefabSystem);
				entities.Dispose();
			}
		}
	}
```

- `public StoreDefaultData(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public void StoreDefaultData(EntityManager entityManager, PrefabSystem prefabSystem)
	{
		for (int i = 0; i < m_GlobalModePrefabs.Count; i++)
		{
			EntityQuery entityQuery = entityManager.CreateEntityQuery(m_GlobalModePrefabs[i].GetEntityQueryDesc());
			if (!entityQuery.IsEmptyIgnoreFilter)
			{
				NativeArray<Entity> requestedQuery = entityQuery.ToEntityArray(Allocator.TempJob);
				m_GlobalModePrefabs[i].StoreDefaultData(entityManager, ref requestedQuery, prefabSystem);
				requestedQuery.Dispose();
			}
		}
	}
```


