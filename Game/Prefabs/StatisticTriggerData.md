# Game.Prefabs.StatisticTriggerData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct StatisticTriggerData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Game.Prefabs.StatisticTriggerType m_Type;
    public Unity.Entities.Entity m_StatisticEntity;
    public System.Int32 m_StatisticParameter;
    public Unity.Entities.Entity m_NormalizeWithPrefab;
    public System.Int32 m_NormalizeWithParameter;
    public System.Int32 m_TimeFrame;
    public System.Int32 m_MinSamples;

}
```


## Fields

- `public Game.Prefabs.StatisticTriggerType m_Type`  

```csharp
public Game.Prefabs.StatisticTriggerType m_Type;
```

- `public Unity.Entities.Entity m_StatisticEntity`  

```csharp
public Unity.Entities.Entity m_StatisticEntity;
```

- `public System.Int32 m_StatisticParameter`  

```csharp
public System.Int32 m_StatisticParameter;
```

- `public Unity.Entities.Entity m_NormalizeWithPrefab`  

```csharp
public Unity.Entities.Entity m_NormalizeWithPrefab;
```

- `public System.Int32 m_NormalizeWithParameter`  

```csharp
public System.Int32 m_NormalizeWithParameter;
```

- `public System.Int32 m_TimeFrame`  

```csharp
public System.Int32 m_TimeFrame;
```

- `public System.Int32 m_MinSamples`  

```csharp
public System.Int32 m_MinSamples;
```


