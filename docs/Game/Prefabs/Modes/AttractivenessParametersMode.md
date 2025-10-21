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
public virtual Unity.Jobs.JobHandle ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps);
```

- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public virtual Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
```

- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
```


