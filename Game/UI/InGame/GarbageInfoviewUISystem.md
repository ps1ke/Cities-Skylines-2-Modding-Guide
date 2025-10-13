# Game.UI.InGame.GarbageInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GarbageInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Simulation.GarbageAccumulationSystem m_GarbageAccumulationSystem;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_Capacity;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_StoredGarbage;
    private Colossal.UI.Binding.GetterValueBinding<System.Single> m_ProcessingRate;
    private Colossal.UI.Binding.GetterValueBinding<System.Single> m_GarbageRate;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_ProcessingAvailability;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_LandfillAvailability;
    private Unity.Entities.EntityQuery m_GarbageFacilityQuery;
    private Unity.Entities.EntityQuery m_GarbageFacilityModifiedQuery;
    private Unity.Collections.NativeArray<System.Single> m_Results;
    private Game.UI.InGame.GarbageInfoviewUISystem+TypeHandle __TypeHandle;
    private static const System.String kGroup;

    protected System.Boolean Active { protected get; }
    protected System.Boolean Modified { protected get; }

    public GarbageInfoviewUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Single <OnCreate>b__11_0();
    private System.Int32 GetGarbageCapacity();
    private Game.UI.InGame.IndicatorValue GetLandfillAvailability();
    private Game.UI.InGame.IndicatorValue GetProcessingAvailability();
    private System.Single GetProcessingRate();
    private System.Int32 GetStoredGarbage();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void PerformUpdate();
    private System.Void ResetResults();
}
```


## Fields

- `private Game.Simulation.GarbageAccumulationSystem m_GarbageAccumulationSystem`  

```csharp
private Game.Simulation.GarbageAccumulationSystem m_GarbageAccumulationSystem;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_Capacity`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_Capacity;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_StoredGarbage`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_StoredGarbage;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Single> m_ProcessingRate`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Single> m_ProcessingRate;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Single> m_GarbageRate`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Single> m_GarbageRate;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_ProcessingAvailability`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_ProcessingAvailability;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_LandfillAvailability`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_LandfillAvailability;
```

- `private Unity.Entities.EntityQuery m_GarbageFacilityQuery`  

```csharp
private Unity.Entities.EntityQuery m_GarbageFacilityQuery;
```

- `private Unity.Entities.EntityQuery m_GarbageFacilityModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_GarbageFacilityModifiedQuery;
```

- `private Unity.Collections.NativeArray<System.Single> m_Results`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_Results;
```

- `private Game.UI.InGame.GarbageInfoviewUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.GarbageInfoviewUISystem+TypeHandle __TypeHandle;
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

- `public GarbageInfoviewUISystem()`  

```csharp
public GarbageInfoviewUISystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private <OnCreate>b__11_0() : System.Single`  

```csharp
private System.Single <OnCreate>b__11_0();
```

- `private GetGarbageCapacity() : System.Int32`  

```csharp
private System.Int32 GetGarbageCapacity();
```

- `private GetLandfillAvailability() : Game.UI.InGame.IndicatorValue`  

```csharp
private Game.UI.InGame.IndicatorValue GetLandfillAvailability();
```

- `private GetProcessingAvailability() : Game.UI.InGame.IndicatorValue`  

```csharp
private Game.UI.InGame.IndicatorValue GetProcessingAvailability();
```

- `private GetProcessingRate() : System.Single`  

```csharp
private System.Single GetProcessingRate();
```

- `private GetStoredGarbage() : System.Int32`  

```csharp
private System.Int32 GetStoredGarbage();
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

- `Game.UI.InGame.GarbageInfoviewUISystem+Result`  
- `Game.UI.InGame.GarbageInfoviewUISystem+UpdateGarbageJob`  
- `Game.UI.InGame.GarbageInfoviewUISystem+TypeHandle`  

