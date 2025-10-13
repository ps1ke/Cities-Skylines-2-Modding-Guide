# Game.Prefabs.Modes.AttractivenessParametersMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class AttractivenessParametersMode : Game.Prefabs.Modes.EntityQueryModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Single m_ForestEffect;
    public System.Single m_ForestDistance;
    public System.Single m_ShoreEffect;
    public System.Single m_ShoreDistance;
    public Unity.Mathematics.float3 m_HeightBonus;
    public Unity.Mathematics.float2 m_AttractiveTemperature;
    public Unity.Mathematics.float2 m_ExtremeTemperature;
    public Unity.Mathematics.float2 m_TemperatureAffect;
    public Unity.Mathematics.float2 m_RainEffectRange;
    public Unity.Mathematics.float2 m_SnowEffectRange;
    public Unity.Mathematics.float3 m_SnowRainExtremeAffect;

    public AttractivenessParametersMode();

    public virtual Unity.Jobs.JobHandle ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps);
    public virtual Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    protected virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public System.Single m_ForestEffect`  

```csharp
public System.Single m_ForestEffect;
```

- `public System.Single m_ForestDistance`  

```csharp
public System.Single m_ForestDistance;
```

- `public System.Single m_ShoreEffect`  

```csharp
public System.Single m_ShoreEffect;
```

- `public System.Single m_ShoreDistance`  

```csharp
public System.Single m_ShoreDistance;
```

- `public Unity.Mathematics.float3 m_HeightBonus`  

```csharp
public Unity.Mathematics.float3 m_HeightBonus;
```

- `public Unity.Mathematics.float2 m_AttractiveTemperature`  

```csharp
public Unity.Mathematics.float2 m_AttractiveTemperature;
```

- `public Unity.Mathematics.float2 m_ExtremeTemperature`  

```csharp
public Unity.Mathematics.float2 m_ExtremeTemperature;
```

- `public Unity.Mathematics.float2 m_TemperatureAffect`  

```csharp
public Unity.Mathematics.float2 m_TemperatureAffect;
```

- `public Unity.Mathematics.float2 m_RainEffectRange`  

```csharp
public Unity.Mathematics.float2 m_RainEffectRange;
```

- `public Unity.Mathematics.float2 m_SnowEffectRange`  

```csharp
public Unity.Mathematics.float2 m_SnowEffectRange;
```

- `public Unity.Mathematics.float3 m_SnowRainExtremeAffect`  

```csharp
public Unity.Mathematics.float3 m_SnowRainExtremeAffect;
```


## Constructors

- `public AttractivenessParametersMode()`  

```csharp
public AttractivenessParametersMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  

```csharp
public override JobHandle ApplyModeData(EntityManager entityManager, EntityQuery requestedQuery, JobHandle deps)
	{
		Entity singletonEntity = requestedQuery.GetSingletonEntity();
		AttractivenessParameterData componentData = entityManager.GetComponentData<AttractivenessParameterData>(singletonEntity);
		componentData.m_ForestEffect = m_ForestEffect;
		componentData.m_ForestDistance = m_ForestDistance;
		componentData.m_ShoreEffect = m_ShoreEffect;
		componentData.m_ShoreDistance = m_ShoreDistance;
		componentData.m_HeightBonus = m_HeightBonus;
		componentData.m_AttractiveTemperature = m_AttractiveTemperature;
		componentData.m_ExtremeTemperature = m_ExtremeTemperature;
		componentData.m_TemperatureAffect = m_TemperatureAffect;
		componentData.m_RainEffectRange = m_RainEffectRange;
		componentData.m_SnowEffectRange = m_SnowEffectRange;
		componentData.m_SnowRainExtremeAffect = m_SnowRainExtremeAffect;
		entityManager.SetComponentData(singletonEntity, componentData);
		return deps;
	}
```

- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public override EntityQueryDesc GetEntityQueryDesc()
	{
		EntityQueryDesc entityQueryDesc = new EntityQueryDesc();
		entityQueryDesc.All = new ComponentType[1] { ComponentType.ReadOnly<AttractivenessParameterData>() };
		return entityQueryDesc;
	}
```

- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected override void RecordChanges(EntityManager entityManager, Entity entity)
	{
		entityManager.GetComponentData<AttractivenessParameterData>(entity);
	}
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public override void RestoreDefaultData(EntityManager entityManager, ref NativeArray<Entity> entities, PrefabSystem prefabSystem)
	{
		Entity entity = entities[0];
		AttractivenessParametersPrefab attractivenessParametersPrefab = prefabSystem.GetPrefab<AttractivenessParametersPrefab>(entity);
		AttractivenessParameterData componentData = entityManager.GetComponentData<AttractivenessParameterData>(entity);
		componentData.m_ForestEffect = attractivenessParametersPrefab.m_ForestEffect;
		componentData.m_ForestDistance = attractivenessParametersPrefab.m_ForestDistance;
		componentData.m_ShoreEffect = attractivenessParametersPrefab.m_ShoreEffect;
		componentData.m_ShoreDistance = attractivenessParametersPrefab.m_ShoreDistance;
		componentData.m_HeightBonus = attractivenessParametersPrefab.m_HeightBonus;
		componentData.m_AttractiveTemperature = attractivenessParametersPrefab.m_AttractiveTemperature;
		componentData.m_ExtremeTemperature = attractivenessParametersPrefab.m_ExtremeTemperature;
		componentData.m_TemperatureAffect = attractivenessParametersPrefab.m_TemperatureAffect;
		componentData.m_RainEffectRange = attractivenessParametersPrefab.m_RainEffectRange;
		componentData.m_SnowEffectRange = attractivenessParametersPrefab.m_SnowEffectRange;
		componentData.m_SnowRainExtremeAffect = attractivenessParametersPrefab.m_SnowRainExtremeAffect;
		entityManager.SetComponentData(entity, componentData);
	}
```


