# Game.Prefabs.DemandPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class DemandPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.PrefabBase m_ForestryPrefab;
    public Game.Prefabs.PrefabBase m_OfficePrefab;
    public System.Int32 m_MinimumHappiness;
    public System.Single m_HappinessEffect;
    public Unity.Mathematics.float3 m_TaxEffect;
    public System.Single m_StudentEffect;
    public System.Single m_AvailableWorkplaceEffect;
    public System.Single m_HomelessEffect;
    public System.Int32 m_NeutralHappiness;
    public System.Single m_NeutralUnemployment;
    public System.Single m_NeutralAvailableWorkplacePercentage;
    public System.Int32 m_NeutralHomelessness;
    public Unity.Mathematics.int3 m_FreeResidentialRequirement;
    public System.Single m_FreeCommercialProportion;
    public System.Single m_FreeIndustrialProportion;
    public System.Single m_CommercialStorageMinimum;
    public System.Single m_CommercialStorageEffect;
    public System.Single m_CommercialBaseDemand;
    public System.Single m_IndustrialStorageMinimum;
    public System.Single m_IndustrialStorageEffect;
    public System.Single m_IndustrialBaseDemand;
    public System.Single m_ExtractorBaseDemand;
    public System.Single m_StorageDemandMultiplier;
    public System.Int32 m_CommuterWorkerRatioLimit;
    public System.Int32 m_CommuterSlowSpawnFactor;
    public Unity.Mathematics.float4 m_CommuterOCSpawnParameters;
    public Unity.Mathematics.float4 m_TouristOCSpawnParameters;
    public Unity.Mathematics.float4 m_CitizenOCSpawnParameters;
    public System.Single m_TeenSpawnPercentage;
    public Unity.Mathematics.int3 m_FrameIntervalForSpawning;
    public System.Single m_HouseholdSpawnSpeedFactor;
    public System.Single m_HotelRoomPercentRequirement;
    public Unity.Mathematics.float4 m_NewCitizenEducationParameters;

    public DemandPrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.PrefabBase m_ForestryPrefab`  

```csharp
public Game.Prefabs.PrefabBase m_ForestryPrefab;
```

- `public Game.Prefabs.PrefabBase m_OfficePrefab`  

```csharp
public Game.Prefabs.PrefabBase m_OfficePrefab;
```

- `public System.Int32 m_MinimumHappiness`  

```csharp
public System.Int32 m_MinimumHappiness;
```

- `public System.Single m_HappinessEffect`  

```csharp
public System.Single m_HappinessEffect;
```

- `public Unity.Mathematics.float3 m_TaxEffect`  

```csharp
public Unity.Mathematics.float3 m_TaxEffect;
```

- `public System.Single m_StudentEffect`  

```csharp
public System.Single m_StudentEffect;
```

- `public System.Single m_AvailableWorkplaceEffect`  

```csharp
public System.Single m_AvailableWorkplaceEffect;
```

- `public System.Single m_HomelessEffect`  

```csharp
public System.Single m_HomelessEffect;
```

- `public System.Int32 m_NeutralHappiness`  

```csharp
public System.Int32 m_NeutralHappiness;
```

- `public System.Single m_NeutralUnemployment`  

```csharp
public System.Single m_NeutralUnemployment;
```

- `public System.Single m_NeutralAvailableWorkplacePercentage`  

```csharp
public System.Single m_NeutralAvailableWorkplacePercentage;
```

- `public System.Int32 m_NeutralHomelessness`  

```csharp
public System.Int32 m_NeutralHomelessness;
```

- `public Unity.Mathematics.int3 m_FreeResidentialRequirement`  

```csharp
public Unity.Mathematics.int3 m_FreeResidentialRequirement;
```

- `public System.Single m_FreeCommercialProportion`  

```csharp
public System.Single m_FreeCommercialProportion;
```

- `public System.Single m_FreeIndustrialProportion`  

```csharp
public System.Single m_FreeIndustrialProportion;
```

- `public System.Single m_CommercialStorageMinimum`  

```csharp
public System.Single m_CommercialStorageMinimum;
```

- `public System.Single m_CommercialStorageEffect`  

```csharp
public System.Single m_CommercialStorageEffect;
```

- `public System.Single m_CommercialBaseDemand`  

```csharp
public System.Single m_CommercialBaseDemand;
```

- `public System.Single m_IndustrialStorageMinimum`  

```csharp
public System.Single m_IndustrialStorageMinimum;
```

- `public System.Single m_IndustrialStorageEffect`  

```csharp
public System.Single m_IndustrialStorageEffect;
```

- `public System.Single m_IndustrialBaseDemand`  

```csharp
public System.Single m_IndustrialBaseDemand;
```

- `public System.Single m_ExtractorBaseDemand`  

```csharp
public System.Single m_ExtractorBaseDemand;
```

- `public System.Single m_StorageDemandMultiplier`  

```csharp
public System.Single m_StorageDemandMultiplier;
```

- `public System.Int32 m_CommuterWorkerRatioLimit`  

```csharp
public System.Int32 m_CommuterWorkerRatioLimit;
```

- `public System.Int32 m_CommuterSlowSpawnFactor`  

```csharp
public System.Int32 m_CommuterSlowSpawnFactor;
```

- `public Unity.Mathematics.float4 m_CommuterOCSpawnParameters`  

```csharp
public Unity.Mathematics.float4 m_CommuterOCSpawnParameters;
```

- `public Unity.Mathematics.float4 m_TouristOCSpawnParameters`  

```csharp
public Unity.Mathematics.float4 m_TouristOCSpawnParameters;
```

- `public Unity.Mathematics.float4 m_CitizenOCSpawnParameters`  

```csharp
public Unity.Mathematics.float4 m_CitizenOCSpawnParameters;
```

- `public System.Single m_TeenSpawnPercentage`  

```csharp
public System.Single m_TeenSpawnPercentage;
```

- `public Unity.Mathematics.int3 m_FrameIntervalForSpawning`  

```csharp
public Unity.Mathematics.int3 m_FrameIntervalForSpawning;
```

- `public System.Single m_HouseholdSpawnSpeedFactor`  

```csharp
public System.Single m_HouseholdSpawnSpeedFactor;
```

- `public System.Single m_HotelRoomPercentRequirement`  

```csharp
public System.Single m_HotelRoomPercentRequirement;
```

- `public Unity.Mathematics.float4 m_NewCitizenEducationParameters`  

```csharp
public Unity.Mathematics.float4 m_NewCitizenEducationParameters;
```


## Constructors

- `public DemandPrefab()`  

```csharp
public DemandPrefab();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		base.GetArchetypeComponents(components);
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<DemandParameterData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem orCreateSystemManaged = entityManager.World.GetOrCreateSystemManaged<PrefabSystem>();
		entityManager.SetComponentData(entity, new DemandParameterData
		{
			m_ForestryPrefab = orCreateSystemManaged.GetEntity(m_ForestryPrefab),
			m_OfficePrefab = orCreateSystemManaged.GetEntity(m_OfficePrefab),
			m_MinimumHappiness = m_MinimumHappiness,
			m_HappinessEffect = m_HappinessEffect,
			m_AvailableWorkplaceEffect = m_AvailableWorkplaceEffect,
			m_HomelessEffect = m_HomelessEffect,
			m_NeutralHappiness = m_NeutralHappiness,
			m_NeutralAvailableWorkplacePercentage = m_NeutralAvailableWorkplacePercentage,
			m_NeutralHomelessness = m_NeutralHomelessness,
			m_FreeResidentialRequirement = m_FreeResidentialRequirement,
			m_FreeCommercialProportion = m_FreeCommercialProportion,
			m_FreeIndustrialProportion = m_FreeIndustrialProportion,
			m_CommercialStorageMinimum = m_CommercialStorageMinimum,
			m_CommercialStorageEffect = m_CommercialStorageEffect,
			m_CommercialBaseDemand = m_CommercialBaseDemand,
			m_IndustrialStorageMinimum = m_IndustrialStorageMinimum,
			m_IndustrialStorageEffect = m_IndustrialStorageEffect,
			m_IndustrialBaseDemand = m_IndustrialBaseDemand,
			m_ExtractorBaseDemand = m_ExtractorBaseDemand,
			m_StorageDemandMultiplier = m_StorageDemandMultiplier,
			m_CommuterWorkerRatioLimit = m_CommuterWorkerRatioLimit,
			m_CommuterSlowSpawnFactor = m_CommuterSlowSpawnFactor,
			m_CommuterOCSpawnParameters = m_CommuterOCSpawnParameters,
			m_TouristOCSpawnParameters = m_TouristOCSpawnParameters,
			m_CitizenOCSpawnParameters = m_CitizenOCSpawnParameters,
			m_TeenSpawnPercentage = m_TeenSpawnPercentage,
			m_FrameIntervalForSpawning = m_FrameIntervalForSpawning,
			m_NeutralUnemployment = m_NeutralUnemployment,
			m_TaxEffect = m_TaxEffect,
			m_StudentEffect = m_StudentEffect,
			m_HouseholdSpawnSpeedFactor = m_HouseholdSpawnSpeedFactor,
			m_NewCitizenEducationParameters = m_NewCitizenEducationParameters,
			m_HotelRoomPercentRequirement = m_HotelRoomPercentRequirement
		});
	}
```


