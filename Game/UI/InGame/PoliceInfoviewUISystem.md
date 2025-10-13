# Game.UI.InGame.PoliceInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PoliceInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_CrimeProducers;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_CrimeProbability;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_JailCapacity;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_ArrestedCriminals;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_InJail;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_PrisonCapacity;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_Prisoners;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_InPrison;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_Criminals;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_CrimePerMonth;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_EscapedRate;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_AverageCrimeProbability;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_JailAvailability;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_PrisonAvailability;
    private Unity.Entities.EntityQuery m_PrisonQuery;
    private Unity.Entities.EntityQuery m_PrisonModifiedQuery;
    private Unity.Entities.EntityQuery m_CriminalQuery;
    private Unity.Entities.EntityQuery m_PoliceStationQuery;
    private Unity.Entities.EntityQuery m_PoliceStationModifiedQuery;
    private Unity.Entities.EntityQuery m_CrimeProducerQuery;
    private Unity.Entities.EntityQuery m_CrimeProducerModifiedQuery;
    private Unity.Collections.NativeArray<System.Single> m_Results;
    private Game.UI.InGame.PoliceInfoviewUISystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_632591896_0;
    private static const System.String kGroup;

    protected System.Boolean Active { protected get; }
    protected System.Boolean Modified { protected get; }

    public PoliceInfoviewUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Game.UI.InGame.IndicatorValue GetCrimeProbability();
    private Game.UI.InGame.IndicatorValue GetJailAvailability();
    private Game.UI.InGame.IndicatorValue GetPrisonAvailability();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void PerformUpdate();
    private System.Void ResetResults();
}
```


## Fields

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_CrimeProducers`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_CrimeProducers;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_CrimeProbability`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_CrimeProbability;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_JailCapacity`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_JailCapacity;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_ArrestedCriminals`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_ArrestedCriminals;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_InJail`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_InJail;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_PrisonCapacity`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_PrisonCapacity;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_Prisoners`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_Prisoners;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_InPrison`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_InPrison;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_Criminals`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_Criminals;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_CrimePerMonth`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_CrimePerMonth;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_EscapedRate`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_EscapedRate;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_AverageCrimeProbability`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_AverageCrimeProbability;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_JailAvailability`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_JailAvailability;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_PrisonAvailability`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_PrisonAvailability;
```

- `private Unity.Entities.EntityQuery m_PrisonQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrisonQuery;
```

- `private Unity.Entities.EntityQuery m_PrisonModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrisonModifiedQuery;
```

- `private Unity.Entities.EntityQuery m_CriminalQuery`  

```csharp
private Unity.Entities.EntityQuery m_CriminalQuery;
```

- `private Unity.Entities.EntityQuery m_PoliceStationQuery`  

```csharp
private Unity.Entities.EntityQuery m_PoliceStationQuery;
```

- `private Unity.Entities.EntityQuery m_PoliceStationModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_PoliceStationModifiedQuery;
```

- `private Unity.Entities.EntityQuery m_CrimeProducerQuery`  

```csharp
private Unity.Entities.EntityQuery m_CrimeProducerQuery;
```

- `private Unity.Entities.EntityQuery m_CrimeProducerModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_CrimeProducerModifiedQuery;
```

- `private Unity.Collections.NativeArray<System.Single> m_Results`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_Results;
```

- `private Game.UI.InGame.PoliceInfoviewUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.PoliceInfoviewUISystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_632591896_0`  

```csharp
private Unity.Entities.EntityQuery __query_632591896_0;
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

- `public PoliceInfoviewUISystem()`  

```csharp
public PoliceInfoviewUISystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private GetCrimeProbability() : Game.UI.InGame.IndicatorValue`  

```csharp
private Game.UI.InGame.IndicatorValue GetCrimeProbability();
```

- `private GetJailAvailability() : Game.UI.InGame.IndicatorValue`  

```csharp
private Game.UI.InGame.IndicatorValue GetJailAvailability();
```

- `private GetPrisonAvailability() : Game.UI.InGame.IndicatorValue`  

```csharp
private Game.UI.InGame.IndicatorValue GetPrisonAvailability();
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

- `private ResetResults() : System.Void`  

```csharp
private System.Void ResetResults();
```


## Nested types

- `Game.UI.InGame.PoliceInfoviewUISystem+Result`  
- `Game.UI.InGame.PoliceInfoviewUISystem+PoliceStationJob`  
- `Game.UI.InGame.PoliceInfoviewUISystem+PrisonJob`  
- `Game.UI.InGame.PoliceInfoviewUISystem+CrimeProducerJob`  
- `Game.UI.InGame.PoliceInfoviewUISystem+CriminalJob`  
- `Game.UI.InGame.PoliceInfoviewUISystem+TypeHandle`  

