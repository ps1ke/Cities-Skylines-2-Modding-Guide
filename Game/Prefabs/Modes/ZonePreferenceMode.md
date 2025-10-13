# Game.Prefabs.Modes.ZonePreferenceMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ZonePreferenceMode : Game.Prefabs.Modes.EntityQueryModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Single m_ResidentialSignificanceServices;
    public System.Single m_ResidentialSignificanceWorkplaces;
    public System.Single m_ResidentialSignificanceLandValue;
    public System.Single m_ResidentialSignificancePollution;
    public System.Single m_ResidentialNeutralLandValue;
    public System.Single m_CommercialSignificanceConsumers;
    public System.Single m_CommercialSignificanceCompetitors;
    public System.Single m_CommercialSignificanceWorkplaces;
    public System.Single m_CommercialSignificanceLandValue;
    public System.Single m_CommercialNeutralLandValue;
    public System.Single m_IndustrialSignificanceInput;
    public System.Single m_IndustrialSignificanceOutside;
    public System.Single m_IndustrialSignificanceLandValue;
    public System.Single m_IndustrialNeutralLandValue;
    public System.Single m_OfficeSignificanceEmployees;
    public System.Single m_OfficeSignificanceServices;

    public ZonePreferenceMode();

    public virtual Unity.Jobs.JobHandle ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps);
    public virtual Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    protected virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public System.Single m_ResidentialSignificanceServices`  

```csharp
public System.Single m_ResidentialSignificanceServices;
```

- `public System.Single m_ResidentialSignificanceWorkplaces`  

```csharp
public System.Single m_ResidentialSignificanceWorkplaces;
```

- `public System.Single m_ResidentialSignificanceLandValue`  

```csharp
public System.Single m_ResidentialSignificanceLandValue;
```

- `public System.Single m_ResidentialSignificancePollution`  

```csharp
public System.Single m_ResidentialSignificancePollution;
```

- `public System.Single m_ResidentialNeutralLandValue`  

```csharp
public System.Single m_ResidentialNeutralLandValue;
```

- `public System.Single m_CommercialSignificanceConsumers`  

```csharp
public System.Single m_CommercialSignificanceConsumers;
```

- `public System.Single m_CommercialSignificanceCompetitors`  

```csharp
public System.Single m_CommercialSignificanceCompetitors;
```

- `public System.Single m_CommercialSignificanceWorkplaces`  

```csharp
public System.Single m_CommercialSignificanceWorkplaces;
```

- `public System.Single m_CommercialSignificanceLandValue`  

```csharp
public System.Single m_CommercialSignificanceLandValue;
```

- `public System.Single m_CommercialNeutralLandValue`  

```csharp
public System.Single m_CommercialNeutralLandValue;
```

- `public System.Single m_IndustrialSignificanceInput`  

```csharp
public System.Single m_IndustrialSignificanceInput;
```

- `public System.Single m_IndustrialSignificanceOutside`  

```csharp
public System.Single m_IndustrialSignificanceOutside;
```

- `public System.Single m_IndustrialSignificanceLandValue`  

```csharp
public System.Single m_IndustrialSignificanceLandValue;
```

- `public System.Single m_IndustrialNeutralLandValue`  

```csharp
public System.Single m_IndustrialNeutralLandValue;
```

- `public System.Single m_OfficeSignificanceEmployees`  

```csharp
public System.Single m_OfficeSignificanceEmployees;
```

- `public System.Single m_OfficeSignificanceServices`  

```csharp
public System.Single m_OfficeSignificanceServices;
```


## Constructors

- `public ZonePreferenceMode()`  

```csharp
public ZonePreferenceMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  

```csharp
public override JobHandle ApplyModeData(EntityManager entityManager, EntityQuery requestedQuery, JobHandle deps)
	{
		Entity singletonEntity = requestedQuery.GetSingletonEntity();
		ZonePreferenceData componentData = entityManager.GetComponentData<ZonePreferenceData>(singletonEntity);
		componentData.m_ResidentialSignificanceServices = m_ResidentialSignificanceServices;
		componentData.m_ResidentialSignificanceWorkplaces = m_ResidentialSignificanceWorkplaces;
		componentData.m_ResidentialSignificanceLandValue = m_ResidentialSignificanceLandValue;
		componentData.m_ResidentialSignificancePollution = m_ResidentialSignificancePollution;
		componentData.m_ResidentialNeutralLandValue = m_ResidentialNeutralLandValue;
		componentData.m_CommercialSignificanceConsumers = m_CommercialSignificanceConsumers;
		componentData.m_CommercialSignificanceCompetitors = m_CommercialSignificanceCompetitors;
		componentData.m_CommercialSignificanceWorkplaces = m_CommercialSignificanceWorkplaces;
		componentData.m_CommercialSignificanceLandValue = m_CommercialSignificanceLandValue;
		componentData.m_CommercialNeutralLandValue = m_CommercialNeutralLandValue;
		componentData.m_IndustrialSignificanceInput = m_IndustrialSignificanceInput;
		componentData.m_IndustrialSignificanceOutside = m_IndustrialSignificanceOutside;
		componentData.m_IndustrialSignificanceLandValue = m_IndustrialSignificanceLandValue;
		componentData.m_IndustrialNeutralLandValue = m_IndustrialNeutralLandValue;
		componentData.m_OfficeSignificanceEmployees = m_OfficeSignificanceEmployees;
		componentData.m_OfficeSignificanceServices = m_OfficeSignificanceServices;
		entityManager.SetComponentData(singletonEntity, componentData);
		return deps;
	}
```

- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public override EntityQueryDesc GetEntityQueryDesc()
	{
		EntityQueryDesc entityQueryDesc = new EntityQueryDesc();
		entityQueryDesc.All = new ComponentType[1] { ComponentType.ReadOnly<ZonePreferenceData>() };
		return entityQueryDesc;
	}
```

- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected override void RecordChanges(EntityManager entityManager, Entity entity)
	{
		entityManager.GetComponentData<ZonePreferenceData>(entity);
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, ref NativeArray<Entity> entities, PrefabSystem prefabSystem)
	{
		Entity entity = entities[0];
		ZonePreferencePrefab zonePreferencePrefab = prefabSystem.GetPrefab<ZonePreferencePrefab>(entity);
		ZonePreferenceData componentData = entityManager.GetComponentData<ZonePreferenceData>(entity);
		componentData.m_ResidentialSignificanceServices = zonePreferencePrefab.m_ResidentialSignificanceServices;
		componentData.m_ResidentialSignificanceWorkplaces = zonePreferencePrefab.m_ResidentialSignificanceWorkplaces;
		componentData.m_ResidentialSignificanceLandValue = zonePreferencePrefab.m_ResidentialSignificanceLandValue;
		componentData.m_ResidentialSignificancePollution = zonePreferencePrefab.m_ResidentialSignificancePollution;
		componentData.m_ResidentialNeutralLandValue = zonePreferencePrefab.m_ResidentialNeutralLandValue;
		componentData.m_CommercialSignificanceConsumers = zonePreferencePrefab.m_CommercialSignificanceConsumers;
		componentData.m_CommercialSignificanceCompetitors = zonePreferencePrefab.m_CommercialSignificanceCompetitors;
		componentData.m_CommercialSignificanceWorkplaces = zonePreferencePrefab.m_CommercialSignificanceWorkplaces;
		componentData.m_CommercialSignificanceLandValue = zonePreferencePrefab.m_CommercialSignificanceLandValue;
		componentData.m_CommercialNeutralLandValue = zonePreferencePrefab.m_CommercialNeutralLandValue;
		componentData.m_IndustrialSignificanceInput = zonePreferencePrefab.m_IndustrialSignificanceInput;
		componentData.m_IndustrialSignificanceOutside = zonePreferencePrefab.m_IndustrialSignificanceOutside;
		componentData.m_IndustrialSignificanceLandValue = zonePreferencePrefab.m_IndustrialSignificanceLandValue;
		componentData.m_IndustrialNeutralLandValue = zonePreferencePrefab.m_IndustrialNeutralLandValue;
		componentData.m_OfficeSignificanceEmployees = zonePreferencePrefab.m_OfficeSignificanceEmployees;
		componentData.m_OfficeSignificanceServices = zonePreferencePrefab.m_OfficeSignificanceServices;
		entityManager.SetComponentData(entity, componentData);
	}
```


