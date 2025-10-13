# Game.Prefabs.PoliceConfigurationData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct PoliceConfigurationData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.Entity m_PoliceServicePrefab;
    public Unity.Entities.Entity m_TrafficAccidentNotificationPrefab;
    public Unity.Entities.Entity m_CrimeSceneNotificationPrefab;
    public System.Single m_MaxCrimeAccumulation;
    public System.Single m_CrimeAccumulationTolerance;
    public System.Int32 m_HomeCrimeEffect;
    public System.Int32 m_WorkplaceCrimeEffect;
    public System.Single m_WelfareCrimeRecurrenceFactor;
    public System.Single m_CrimePoliceCoverageFactor;
    public System.Single m_CrimePopulationReduction;

}
```


## Fields

- `public Unity.Entities.Entity m_PoliceServicePrefab`  

```csharp
public Unity.Entities.Entity m_PoliceServicePrefab;
```

- `public Unity.Entities.Entity m_TrafficAccidentNotificationPrefab`  

```csharp
public Unity.Entities.Entity m_TrafficAccidentNotificationPrefab;
```

- `public Unity.Entities.Entity m_CrimeSceneNotificationPrefab`  

```csharp
public Unity.Entities.Entity m_CrimeSceneNotificationPrefab;
```

- `public System.Single m_MaxCrimeAccumulation`  

```csharp
public System.Single m_MaxCrimeAccumulation;
```

- `public System.Single m_CrimeAccumulationTolerance`  

```csharp
public System.Single m_CrimeAccumulationTolerance;
```

- `public System.Int32 m_HomeCrimeEffect`  

```csharp
public System.Int32 m_HomeCrimeEffect;
```

- `public System.Int32 m_WorkplaceCrimeEffect`  

```csharp
public System.Int32 m_WorkplaceCrimeEffect;
```

- `public System.Single m_WelfareCrimeRecurrenceFactor`  

```csharp
public System.Single m_WelfareCrimeRecurrenceFactor;
```

- `public System.Single m_CrimePoliceCoverageFactor`  

```csharp
public System.Single m_CrimePoliceCoverageFactor;
```

- `public System.Single m_CrimePopulationReduction`  

```csharp
public System.Single m_CrimePopulationReduction;
```


