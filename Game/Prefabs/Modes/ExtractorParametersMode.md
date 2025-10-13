# Game.Prefabs.Modes.ExtractorParametersMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ExtractorParametersMode : Game.Prefabs.Modes.EntityQueryModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Single m_FertilityConsumption;
    public System.Single m_OreConsumption;
    public System.Single m_ForestConsumption;
    public System.Single m_OilConsumption;
    public System.Single m_FullFertility;
    public System.Single m_FullOre;
    public System.Single m_FullOil;

    public ExtractorParametersMode();

    public virtual Unity.Jobs.JobHandle ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps);
    public virtual Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    protected virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public System.Single m_FertilityConsumption`  

```csharp
public System.Single m_FertilityConsumption;
```

- `public System.Single m_OreConsumption`  

```csharp
public System.Single m_OreConsumption;
```

- `public System.Single m_ForestConsumption`  

```csharp
public System.Single m_ForestConsumption;
```

- `public System.Single m_OilConsumption`  

```csharp
public System.Single m_OilConsumption;
```

- `public System.Single m_FullFertility`  

```csharp
public System.Single m_FullFertility;
```

- `public System.Single m_FullOre`  

```csharp
public System.Single m_FullOre;
```

- `public System.Single m_FullOil`  

```csharp
public System.Single m_FullOil;
```


## Constructors

- `public ExtractorParametersMode()`  

```csharp
public ExtractorParametersMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  

```csharp
public override JobHandle ApplyModeData(EntityManager entityManager, EntityQuery requestedQuery, JobHandle deps)
	{
		Entity singletonEntity = requestedQuery.GetSingletonEntity();
		ExtractorParameterData componentData = entityManager.GetComponentData<ExtractorParameterData>(singletonEntity);
		componentData.m_FertilityConsumption = m_FertilityConsumption;
		componentData.m_OreConsumption = m_OreConsumption;
		componentData.m_ForestConsumption = m_ForestConsumption;
		componentData.m_OilConsumption = m_OilConsumption;
		componentData.m_FullFertility = m_FullFertility;
		componentData.m_FullOre = m_FullOre;
		componentData.m_FullOil = m_FullOil;
		entityManager.SetComponentData(singletonEntity, componentData);
		return deps;
	}
```

- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public override EntityQueryDesc GetEntityQueryDesc()
	{
		EntityQueryDesc entityQueryDesc = new EntityQueryDesc();
		entityQueryDesc.All = new ComponentType[1] { ComponentType.ReadOnly<ExtractorParameterData>() };
		return entityQueryDesc;
	}
```

- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected override void RecordChanges(EntityManager entityManager, Entity entity)
	{
		entityManager.GetComponentData<ExtractorParameterData>(entity);
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, ref NativeArray<Entity> entities, PrefabSystem prefabSystem)
	{
		Entity entity = entities[0];
		ExtractorParameterPrefab extractorParameterPrefab = prefabSystem.GetPrefab<ExtractorParameterPrefab>(entity);
		ExtractorParameterData componentData = entityManager.GetComponentData<ExtractorParameterData>(entity);
		componentData.m_FertilityConsumption = extractorParameterPrefab.m_FertilityConsumption;
		componentData.m_OreConsumption = extractorParameterPrefab.m_OreConsumption;
		componentData.m_ForestConsumption = extractorParameterPrefab.m_ForestConsumption;
		componentData.m_OilConsumption = extractorParameterPrefab.m_OilConsumption;
		componentData.m_FullFertility = extractorParameterPrefab.m_FullFertility;
		componentData.m_FullOre = extractorParameterPrefab.m_FullOre;
		componentData.m_FullOil = extractorParameterPrefab.m_FullOil;
		entityManager.SetComponentData(entity, componentData);
	}
```


