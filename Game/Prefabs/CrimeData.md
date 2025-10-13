# Game.Prefabs.CrimeData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct CrimeData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Game.Prefabs.EventTargetType m_RandomTargetType;
    public Game.Prefabs.CrimeType m_CrimeType;
    public Colossal.Mathematics.Bounds1 m_OccurenceProbability;
    public Colossal.Mathematics.Bounds1 m_RecurrenceProbability;
    public Colossal.Mathematics.Bounds1 m_AlarmDelay;
    public Colossal.Mathematics.Bounds1 m_CrimeDuration;
    public Colossal.Mathematics.Bounds1 m_CrimeIncomeAbsolute;
    public Colossal.Mathematics.Bounds1 m_CrimeIncomeRelative;
    public Colossal.Mathematics.Bounds1 m_JailTimeRange;
    public Colossal.Mathematics.Bounds1 m_PrisonTimeRange;
    public System.Single m_PrisonProbability;

}
```


## Fields

- `public Game.Prefabs.EventTargetType m_RandomTargetType`  

```csharp
public Game.Prefabs.EventTargetType m_RandomTargetType;
```

- `public Game.Prefabs.CrimeType m_CrimeType`  

```csharp
public Game.Prefabs.CrimeType m_CrimeType;
```

- `public Colossal.Mathematics.Bounds1 m_OccurenceProbability`  

```csharp
public Colossal.Mathematics.Bounds1 m_OccurenceProbability;
```

- `public Colossal.Mathematics.Bounds1 m_RecurrenceProbability`  

```csharp
public Colossal.Mathematics.Bounds1 m_RecurrenceProbability;
```

- `public Colossal.Mathematics.Bounds1 m_AlarmDelay`  

```csharp
public Colossal.Mathematics.Bounds1 m_AlarmDelay;
```

- `public Colossal.Mathematics.Bounds1 m_CrimeDuration`  

```csharp
public Colossal.Mathematics.Bounds1 m_CrimeDuration;
```

- `public Colossal.Mathematics.Bounds1 m_CrimeIncomeAbsolute`  

```csharp
public Colossal.Mathematics.Bounds1 m_CrimeIncomeAbsolute;
```

- `public Colossal.Mathematics.Bounds1 m_CrimeIncomeRelative`  

```csharp
public Colossal.Mathematics.Bounds1 m_CrimeIncomeRelative;
```

- `public Colossal.Mathematics.Bounds1 m_JailTimeRange`  

```csharp
public Colossal.Mathematics.Bounds1 m_JailTimeRange;
```

- `public Colossal.Mathematics.Bounds1 m_PrisonTimeRange`  

```csharp
public Colossal.Mathematics.Bounds1 m_PrisonTimeRange;
```

- `public System.Single m_PrisonProbability`  

```csharp
public System.Single m_PrisonProbability;
```


