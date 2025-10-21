# Game.UI.InGame.PopulationInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

## Code

```csharp
public class PopulationInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem;
    private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_Population;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_Employed;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_Jobs;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_Unemployment;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_Homelessness;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_BirthRate;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_DeathRate;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_MovedIn;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_MovedAway;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_Homeless;
    private Colossal.UI.Binding.RawValueBinding m_AgeData;
    private Unity.Entities.EntityQuery m_WorkProviderModifiedQuery;
    private Unity.Entities.EntityQuery m_PopulationModifiedQuery;
    private static const System.String kGroup;

    protected System.Boolean Active { protected get; }
    protected System.Boolean Modified { protected get; }

    public PopulationInfoviewUISystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void PerformUpdate();
    private System.Void UpdateAgeData(Colossal.UI.Binding.IJsonWriter binder);
    private System.Void UpdateBindings();
    private System.Void UpdateStatistics();
}
```


## Fields

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem`  

```csharp
private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem;
```

- `private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem`  

```csharp
private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_Population`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_Population;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_Employed`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_Employed;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_Jobs`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_Jobs;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_Unemployment`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_Unemployment;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_Homelessness`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_Homelessness;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_BirthRate`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_BirthRate;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_DeathRate`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_DeathRate;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_MovedIn`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_MovedIn;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_MovedAway`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_MovedAway;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_Homeless`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_Homeless;
```

- `private Colossal.UI.Binding.RawValueBinding m_AgeData`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_AgeData;
```

- `private Unity.Entities.EntityQuery m_WorkProviderModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_WorkProviderModifiedQuery;
```

- `private Unity.Entities.EntityQuery m_PopulationModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_PopulationModifiedQuery;
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

- `public PopulationInfoviewUISystem()`  

```csharp
public PopulationInfoviewUISystem();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual PerformUpdate() : System.Void`  

```csharp
protected virtual System.Void PerformUpdate();
```

- `private UpdateAgeData(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private System.Void UpdateAgeData(Colossal.UI.Binding.IJsonWriter binder);
```

- `private UpdateBindings() : System.Void`  

```csharp
private System.Void UpdateBindings();
```

- `private UpdateStatistics() : System.Void`  

```csharp
private System.Void UpdateStatistics();
```


