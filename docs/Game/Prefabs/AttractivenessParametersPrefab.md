# Game.Prefabs.AttractivenessParametersPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class AttractivenessParametersPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Single m_ForestEffect;
    public System.Single m_ForestDistance;
    public System.Single m_ShoreEffect;
    public System.Single m_ShoreDistance;
    public Unity.Mathematics.float3 m_HeightBonus;
    public Unity.Mathematics.float2 m_AttractiveTemperature;
    public Unity.Mathematics.float2 m_ExtremeTemperature;
    public Unity.Mathematics.float2 m_RainEffectRange;
    public Unity.Mathematics.float2 m_SnowEffectRange;
    public Unity.Mathematics.float2 m_TemperatureAffect;
    public Unity.Mathematics.float3 m_SnowRainExtremeAffect;

    public AttractivenessParametersPrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
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

- `public Unity.Mathematics.float2 m_RainEffectRange`  

```csharp
public Unity.Mathematics.float2 m_RainEffectRange;
```

- `public Unity.Mathematics.float2 m_SnowEffectRange`  

```csharp
public Unity.Mathematics.float2 m_SnowEffectRange;
```

- `public Unity.Mathematics.float2 m_TemperatureAffect`  

```csharp
public Unity.Mathematics.float2 m_TemperatureAffect;
```

- `public Unity.Mathematics.float3 m_SnowRainExtremeAffect`  

```csharp
public Unity.Mathematics.float3 m_SnowRainExtremeAffect;
```


## Constructors

- `public AttractivenessParametersPrefab()`  

```csharp
public AttractivenessParametersPrefab();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


