# Game.Prefabs.Modes.SoilWaterMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class SoilWaterMode : Game.Prefabs.Modes.EntityQueryModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Single m_RainMultiplier;
    public System.Single m_HeightEffect;
    public System.Single m_MaxDiffusion;
    public System.Single m_WaterPerUnit;
    public System.Single m_MoistureUnderWater;
    public System.Single m_MaximumWaterDepth;
    public System.Single m_OverflowRate;

    public SoilWaterMode();

    public virtual Unity.Jobs.JobHandle ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps);
    public virtual Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    protected virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public System.Single m_RainMultiplier`  

```csharp
public System.Single m_RainMultiplier;
```

- `public System.Single m_HeightEffect`  

```csharp
public System.Single m_HeightEffect;
```

- `public System.Single m_MaxDiffusion`  

```csharp
public System.Single m_MaxDiffusion;
```

- `public System.Single m_WaterPerUnit`  

```csharp
public System.Single m_WaterPerUnit;
```

- `public System.Single m_MoistureUnderWater`  

```csharp
public System.Single m_MoistureUnderWater;
```

- `public System.Single m_MaximumWaterDepth`  

```csharp
public System.Single m_MaximumWaterDepth;
```

- `public System.Single m_OverflowRate`  

```csharp
public System.Single m_OverflowRate;
```


## Constructors

- `public SoilWaterMode()`  

```csharp
public SoilWaterMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  

```csharp
public override JobHandle ApplyModeData(EntityManager entityManager, EntityQuery requestedQuery, JobHandle deps)
	{
		Entity singletonEntity = requestedQuery.GetSingletonEntity();
		SoilWaterParameterData componentData = entityManager.GetComponentData<SoilWaterParameterData>(singletonEntity);
		componentData.m_RainMultiplier = m_RainMultiplier;
		componentData.m_HeightEffect = m_HeightEffect;
		componentData.m_MaxDiffusion = m_MaxDiffusion;
		componentData.m_WaterPerUnit = m_WaterPerUnit;
		componentData.m_MoistureUnderWater = m_MoistureUnderWater;
		componentData.m_MaximumWaterDepth = m_MaximumWaterDepth;
		componentData.m_OverflowRate = m_OverflowRate;
		entityManager.SetComponentData(singletonEntity, componentData);
		return deps;
	}
```

- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public override EntityQueryDesc GetEntityQueryDesc()
	{
		EntityQueryDesc entityQueryDesc = new EntityQueryDesc();
		entityQueryDesc.All = new ComponentType[1] { ComponentType.ReadOnly<SoilWaterParameterData>() };
		return entityQueryDesc;
	}
```

- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected override void RecordChanges(EntityManager entityManager, Entity entity)
	{
		entityManager.GetComponentData<SoilWaterParameterData>(entity);
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, ref NativeArray<Entity> entities, PrefabSystem prefabSystem)
	{
		Entity entity = entities[0];
		SoilWaterPrefab soilWaterPrefab = prefabSystem.GetPrefab<SoilWaterPrefab>(entity);
		SoilWaterParameterData componentData = entityManager.GetComponentData<SoilWaterParameterData>(entity);
		componentData.m_RainMultiplier = soilWaterPrefab.m_RainMultiplier;
		componentData.m_HeightEffect = soilWaterPrefab.m_HeightEffect;
		componentData.m_MaxDiffusion = soilWaterPrefab.m_MaxDiffusion;
		componentData.m_WaterPerUnit = soilWaterPrefab.m_WaterPerUnit;
		componentData.m_MoistureUnderWater = soilWaterPrefab.m_MoistureUnderWater;
		componentData.m_MaximumWaterDepth = soilWaterPrefab.m_MaximumWaterDepth;
		componentData.m_OverflowRate = soilWaterPrefab.m_OverflowRate;
		entityManager.SetComponentData(entity, componentData);
	}
```


