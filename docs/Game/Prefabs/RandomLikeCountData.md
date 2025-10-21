# Game.Prefabs.RandomLikeCountData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct RandomLikeCountData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public System.Single m_EducatedPercentage;
    public System.Single m_UneducatedPercentage;
    public Unity.Mathematics.float2 m_RandomAmountFactor;
    public Unity.Mathematics.float2 m_ActiveDays;
    public System.Single m_ContinuousFactor;
    public Unity.Mathematics.int2 m_GoViralFactor;

}
```


## Fields

- `public System.Single m_EducatedPercentage`  

```csharp
public System.Single m_EducatedPercentage;
```

- `public System.Single m_UneducatedPercentage`  

```csharp
public System.Single m_UneducatedPercentage;
```

- `public Unity.Mathematics.float2 m_RandomAmountFactor`  

```csharp
public Unity.Mathematics.float2 m_RandomAmountFactor;
```

- `public Unity.Mathematics.float2 m_ActiveDays`  

```csharp
public Unity.Mathematics.float2 m_ActiveDays;
```

- `public System.Single m_ContinuousFactor`  

```csharp
public System.Single m_ContinuousFactor;
```

- `public Unity.Mathematics.int2 m_GoViralFactor`  

```csharp
public Unity.Mathematics.int2 m_GoViralFactor;
```


