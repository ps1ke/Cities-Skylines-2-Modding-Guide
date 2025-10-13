# Game.UI.InGame.RoadsInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RoadsInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_ParkingCapacity;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_ParkedCars;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_ParkingIncome;
    private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_ParkingAvailability;
    private Unity.Entities.EntityQuery m_ParkingFacilityQuery;
    private Unity.Entities.EntityQuery m_ParkingFacilityModifiedQuery;
    private Unity.Collections.NativeArray<System.Int32> m_Results;
    private Game.UI.InGame.RoadsInfoviewUISystem+TypeHandle __TypeHandle;
    private static const System.String kGroup;

    protected System.Boolean Active { protected get; }
    protected System.Boolean Modified { protected get; }

    public RoadsInfoviewUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void PerformUpdate();
    private System.Void ResetResults();
    private System.Void UpdateAvailability();
    private System.Void UpdateCapacity();
    private System.Void UpdateIncome();
}
```


## Fields

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_ParkingCapacity`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_ParkingCapacity;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_ParkedCars`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_ParkedCars;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_ParkingIncome`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_ParkingIncome;
```

- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_ParkingAvailability`  

```csharp
private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_ParkingAvailability;
```

- `private Unity.Entities.EntityQuery m_ParkingFacilityQuery`  

```csharp
private Unity.Entities.EntityQuery m_ParkingFacilityQuery;
```

- `private Unity.Entities.EntityQuery m_ParkingFacilityModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_ParkingFacilityModifiedQuery;
```

- `private Unity.Collections.NativeArray<System.Int32> m_Results`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_Results;
```

- `private Game.UI.InGame.RoadsInfoviewUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.RoadsInfoviewUISystem+TypeHandle __TypeHandle;
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

- `public RoadsInfoviewUISystem()`  

```csharp
public RoadsInfoviewUISystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
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

- `private UpdateAvailability() : System.Void`  

```csharp
private System.Void UpdateAvailability();
```

- `private UpdateCapacity() : System.Void`  

```csharp
private System.Void UpdateCapacity();
```

- `private UpdateIncome() : System.Void`  

```csharp
private System.Void UpdateIncome();
```


## Nested types

- `Game.UI.InGame.RoadsInfoviewUISystem+Result`  
- `Game.UI.InGame.RoadsInfoviewUISystem+UpdateParkingJob`  
- `Game.UI.InGame.RoadsInfoviewUISystem+TypeHandle`  

