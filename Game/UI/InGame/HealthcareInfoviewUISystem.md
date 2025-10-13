# Game.UI.InGame.HealthcareInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class HealthcareInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_AverageHealth;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_PatientCount;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_SickCount;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_PatientCapacity;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_DeathRate;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_ProcessingRate;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_CemeteryUse;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_CemeteryCapacity;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_HealthcareAvailability;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_DeathcareAvailability;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_CemeteryAvailability;
    private Unity.Entities.EntityQuery m_HouseholdQuery;
    private Unity.Entities.EntityQuery m_DeathcareFacilityQuery;
    private Unity.Entities.EntityQuery m_HealthcareFacilityQuery;
    private Unity.Entities.EntityQuery m_DeathcareFacilityModifiedQuery;
    private Unity.Entities.EntityQuery m_HealthcareFacilityModifiedQuery;
    private Unity.Collections.NativeArray<System.Single> m_Results;
    private Game.UI.InGame.HealthcareInfoviewUISystem+TypeHandle __TypeHandle;
    private static const System.String kGroup;

    protected System.Boolean Active { protected get; }
    protected System.Boolean Modified { protected get; }

    public HealthcareInfoviewUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Game.UI.InGame.IndicatorValue GetCemeteryAvailability();
    private Game.UI.InGame.IndicatorValue GetDeathcareAvailability();
    private Game.UI.InGame.IndicatorValue GetHealthcareAvailability();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void PerformUpdate();
}
```


## Fields

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_AverageHealth`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_AverageHealth;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_PatientCount`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_PatientCount;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_SickCount`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_SickCount;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_PatientCapacity`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_PatientCapacity;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_DeathRate`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_DeathRate;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_ProcessingRate`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_ProcessingRate;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_CemeteryUse`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_CemeteryUse;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_CemeteryCapacity`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_CemeteryCapacity;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_HealthcareAvailability`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_HealthcareAvailability;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_DeathcareAvailability`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_DeathcareAvailability;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_CemeteryAvailability`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_CemeteryAvailability;
```

- `private Unity.Entities.EntityQuery m_HouseholdQuery`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdQuery;
```

- `private Unity.Entities.EntityQuery m_DeathcareFacilityQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeathcareFacilityQuery;
```

- `private Unity.Entities.EntityQuery m_HealthcareFacilityQuery`  

```csharp
private Unity.Entities.EntityQuery m_HealthcareFacilityQuery;
```

- `private Unity.Entities.EntityQuery m_DeathcareFacilityModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeathcareFacilityModifiedQuery;
```

- `private Unity.Entities.EntityQuery m_HealthcareFacilityModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_HealthcareFacilityModifiedQuery;
```

- `private Unity.Collections.NativeArray<System.Single> m_Results`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_Results;
```

- `private Game.UI.InGame.HealthcareInfoviewUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.HealthcareInfoviewUISystem+TypeHandle __TypeHandle;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `protected System.Boolean Active { protected get }`  

```csharp
protected System.Boolean Active { protected get; }
```

- `protected System.Boolean Modified { protected get }`  

```csharp
protected System.Boolean Modified { protected get; }
```


## Constructors

- `public HealthcareInfoviewUISystem()`  

```csharp
public HealthcareInfoviewUISystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private GetCemeteryAvailability() : Game.UI.InGame.IndicatorValue`  

```csharp
private Game.UI.InGame.IndicatorValue GetCemeteryAvailability();
```

- `private GetDeathcareAvailability() : Game.UI.InGame.IndicatorValue`  

```csharp
private Game.UI.InGame.IndicatorValue GetDeathcareAvailability();
```

- `private GetHealthcareAvailability() : Game.UI.InGame.IndicatorValue`  

```csharp
private Game.UI.InGame.IndicatorValue GetHealthcareAvailability();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual PerformUpdate() : System.Void`  

```csharp
protected virtual System.Void PerformUpdate();
```


## Nested types

- `Game.UI.InGame.HealthcareInfoviewUISystem+Result`  
- `Game.UI.InGame.HealthcareInfoviewUISystem+CalculateAverageHealthJob`  
- `Game.UI.InGame.HealthcareInfoviewUISystem+UpdateHealthcareJob`  
- `Game.UI.InGame.HealthcareInfoviewUISystem+UpdateDeathcareJob`  
- `Game.UI.InGame.HealthcareInfoviewUISystem+TypeHandle`  

