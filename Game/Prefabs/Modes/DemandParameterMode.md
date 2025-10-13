# Game.Prefabs.Modes.DemandParameterMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class DemandParameterMode : Game.Prefabs.Modes.EntityQueryModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
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
    public System.Single m_CommercialBaseDemand;
    public System.Single m_IndustrialBaseDemand;
    public System.Single m_ExtractorBaseDemand;
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

    public DemandParameterMode();

    public virtual Unity.Jobs.JobHandle ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps);
    public virtual Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    protected virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

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

- `public System.Single m_CommercialBaseDemand`  

```csharp
public System.Single m_CommercialBaseDemand;
```

- `public System.Single m_IndustrialBaseDemand`  

```csharp
public System.Single m_IndustrialBaseDemand;
```

- `public System.Single m_ExtractorBaseDemand`  

```csharp
public System.Single m_ExtractorBaseDemand;
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

- `public DemandParameterMode()`  

```csharp
public DemandParameterMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  

```csharp
public override JobHandle ApplyModeData(EntityManager entityManager, EntityQuery requestedQuery, JobHandle deps)
	{
		Entity singletonEntity = requestedQuery.GetSingletonEntity();
		DemandParameterData componentData = entityManager.GetComponentData<DemandParameterData>(singletonEntity);
		componentData.m_MinimumHappiness = m_MinimumHappiness;
		componentData.m_HappinessEffect = m_HappinessEffect;
		componentData.m_TaxEffect = m_TaxEffect;
		componentData.m_StudentEffect = m_StudentEffect;
		componentData.m_AvailableWorkplaceEffect = m_AvailableWorkplaceEffect;
		componentData.m_HomelessEffect = m_HomelessEffect;
		componentData.m_NeutralHappiness = m_NeutralHappiness;
		componentData.m_NeutralUnemployment = m_NeutralUnemployment;
		componentData.m_NeutralAvailableWorkplacePercentage = m_NeutralAvailableWorkplacePercentage;
		componentData.m_NeutralHomelessness = m_NeutralHomelessness;
		componentData.m_FreeResidentialRequirement = m_FreeResidentialRequirement;
		componentData.m_CommercialBaseDemand = m_CommercialBaseDemand;
		componentData.m_IndustrialBaseDemand = m_IndustrialBaseDemand;
		componentData.m_ExtractorBaseDemand = m_ExtractorBaseDemand;
		componentData.m_CommuterWorkerRatioLimit = m_CommuterWorkerRatioLimit;
		componentData.m_CommuterSlowSpawnFactor = m_CommuterSlowSpawnFactor;
		componentData.m_CommuterOCSpawnParameters = m_CommuterOCSpawnParameters;
		componentData.m_TouristOCSpawnParameters = m_TouristOCSpawnParameters;
		componentData.m_CitizenOCSpawnParameters = m_CitizenOCSpawnParameters;
		componentData.m_TeenSpawnPercentage = m_TeenSpawnPercentage;
		componentData.m_FrameIntervalForSpawning = m_FrameIntervalForSpawning;
		componentData.m_HouseholdSpawnSpeedFactor = m_HouseholdSpawnSpeedFactor;
		componentData.m_HotelRoomPercentRequirement = m_HotelRoomPercentRequirement;
		componentData.m_NewCitizenEducationParameters = m_NewCitizenEducationParameters;
		entityManager.SetComponentData(singletonEntity, componentData);
		return deps;
	}
```

- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public override EntityQueryDesc GetEntityQueryDesc()
	{
		EntityQueryDesc entityQueryDesc = new EntityQueryDesc();
		entityQueryDesc.All = new ComponentType[1] { ComponentType.ReadOnly<DemandParameterData>() };
		return entityQueryDesc;
	}
```

- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected override void RecordChanges(EntityManager entityManager, Entity entity)
	{
		entityManager.GetComponentData<DemandParameterData>(entity);
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, ref NativeArray<Entity> entities, PrefabSystem prefabSystem)
	{
		Entity entity = entities[0];
		DemandPrefab demandPrefab = prefabSystem.GetPrefab<DemandPrefab>(entity);
		DemandParameterData componentData = entityManager.GetComponentData<DemandParameterData>(entity);
		componentData.m_MinimumHappiness = demandPrefab.m_MinimumHappiness;
		componentData.m_HappinessEffect = demandPrefab.m_HappinessEffect;
		componentData.m_TaxEffect = demandPrefab.m_TaxEffect;
		componentData.m_StudentEffect = demandPrefab.m_StudentEffect;
		componentData.m_AvailableWorkplaceEffect = demandPrefab.m_AvailableWorkplaceEffect;
		componentData.m_HomelessEffect = demandPrefab.m_HomelessEffect;
		componentData.m_NeutralHappiness = demandPrefab.m_NeutralHappiness;
		componentData.m_NeutralUnemployment = demandPrefab.m_NeutralUnemployment;
		componentData.m_NeutralAvailableWorkplacePercentage = demandPrefab.m_NeutralAvailableWorkplacePercentage;
		componentData.m_NeutralHomelessness = demandPrefab.m_NeutralHomelessness;
		componentData.m_FreeResidentialRequirement = demandPrefab.m_FreeResidentialRequirement;
		componentData.m_CommercialBaseDemand = demandPrefab.m_CommercialBaseDemand;
		componentData.m_IndustrialBaseDemand = demandPrefab.m_IndustrialBaseDemand;
		componentData.m_ExtractorBaseDemand = demandPrefab.m_ExtractorBaseDemand;
		componentData.m_CommuterWorkerRatioLimit = demandPrefab.m_CommuterWorkerRatioLimit;
		componentData.m_CommuterSlowSpawnFactor = demandPrefab.m_CommuterSlowSpawnFactor;
		componentData.m_CommuterOCSpawnParameters = demandPrefab.m_CommuterOCSpawnParameters;
		componentData.m_TouristOCSpawnParameters = demandPrefab.m_TouristOCSpawnParameters;
		componentData.m_CitizenOCSpawnParameters = demandPrefab.m_CitizenOCSpawnParameters;
		componentData.m_TeenSpawnPercentage = demandPrefab.m_TeenSpawnPercentage;
		componentData.m_FrameIntervalForSpawning = demandPrefab.m_FrameIntervalForSpawning;
		componentData.m_HouseholdSpawnSpeedFactor = demandPrefab.m_HouseholdSpawnSpeedFactor;
		componentData.m_HotelRoomPercentRequirement = demandPrefab.m_HotelRoomPercentRequirement;
		componentData.m_NewCitizenEducationParameters = demandPrefab.m_NewCitizenEducationParameters;
		entityManager.SetComponentData(entity, componentData);
	}
```


