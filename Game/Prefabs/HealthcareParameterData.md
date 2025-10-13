# Game.Prefabs.HealthcareParameterData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct HealthcareParameterData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.Entity m_HealthcareServicePrefab;
    public Unity.Entities.Entity m_AmbulanceNotificationPrefab;
    public Unity.Entities.Entity m_HearseNotificationPrefab;
    public Unity.Entities.Entity m_FacilityFullNotificationPrefab;
    public System.Single m_TransportWarningTime;
    public System.Single m_NoResourceTreatmentPenalty;
    public System.Single m_BuildingDestoryDeathRate;
    public Colossal.Collections.AnimationCurve1 m_DeathRate;

}
```


## Fields

- `public Unity.Entities.Entity m_HealthcareServicePrefab`  

```csharp
public Unity.Entities.Entity m_HealthcareServicePrefab;
```

- `public Unity.Entities.Entity m_AmbulanceNotificationPrefab`  

```csharp
public Unity.Entities.Entity m_AmbulanceNotificationPrefab;
```

- `public Unity.Entities.Entity m_HearseNotificationPrefab`  

```csharp
public Unity.Entities.Entity m_HearseNotificationPrefab;
```

- `public Unity.Entities.Entity m_FacilityFullNotificationPrefab`  

```csharp
public Unity.Entities.Entity m_FacilityFullNotificationPrefab;
```

- `public System.Single m_TransportWarningTime`  

```csharp
public System.Single m_TransportWarningTime;
```

- `public System.Single m_NoResourceTreatmentPenalty`  

```csharp
public System.Single m_NoResourceTreatmentPenalty;
```

- `public System.Single m_BuildingDestoryDeathRate`  

```csharp
public System.Single m_BuildingDestoryDeathRate;
```

- `public Colossal.Collections.AnimationCurve1 m_DeathRate`  

```csharp
public Colossal.Collections.AnimationCurve1 m_DeathRate;
```


