# Game.Prefabs.EffectColorData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct EffectColorData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public UnityEngine.Color m_Color;
    public Game.Prefabs.EffectColorSource m_Source;
    public Unity.Mathematics.float3 m_VaritationRanges;

}
```


## Fields

- `public UnityEngine.Color m_Color`  

```csharp
public UnityEngine.Color m_Color;
```

- `public Game.Prefabs.EffectColorSource m_Source`  

```csharp
public Game.Prefabs.EffectColorSource m_Source;
```

- `public Unity.Mathematics.float3 m_VaritationRanges`  

```csharp
public Unity.Mathematics.float3 m_VaritationRanges;
```


