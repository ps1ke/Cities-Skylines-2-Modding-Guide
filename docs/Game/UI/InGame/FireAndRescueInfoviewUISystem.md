# Game.UI.InGame.FireAndRescueInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class FireAndRescueInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Buildings.LocalEffectSystem m_LocalEffectSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.Simulation.FireHazardSystem m_FireHazardSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityQuery m_FlammableQuery;
    private Unity.Entities.EntityQuery m_FireStationsModifiedQuery;
    private Unity.Entities.EntityQuery m_FireConfigQuery;
    private Unity.Collections.NativeArray<System.Single> m_Results;
    private Game.Simulation.EventHelpers+FireHazardData m_FireHazardData;
    private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageFireHazard;
    private Game.UI.InGame.FireAndRescueInfoviewUISystem+TypeHandle __TypeHandle;
    private static const System.String kGroup;

    protected System.Boolean Active { protected get; }
    protected System.Boolean Modified { protected get; }

    public FireAndRescueInfoviewUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void PerformUpdate();
}
```


## Fields

- `private Game.Buildings.LocalEffectSystem m_LocalEffectSystem`  

```csharp
private Game.Buildings.LocalEffectSystem m_LocalEffectSystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.Simulation.FireHazardSystem m_FireHazardSystem`  

```csharp
private Game.Simulation.FireHazardSystem m_FireHazardSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityQuery m_FlammableQuery`  

```csharp
private Unity.Entities.EntityQuery m_FlammableQuery;
```

- `private Unity.Entities.EntityQuery m_FireStationsModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_FireStationsModifiedQuery;
```

- `private Unity.Entities.EntityQuery m_FireConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_FireConfigQuery;
```

- `private Unity.Collections.NativeArray<System.Single> m_Results`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_Results;
```

- `private Game.Simulation.EventHelpers+FireHazardData m_FireHazardData`  

```csharp
private Game.Simulation.EventHelpers+FireHazardData m_FireHazardData;
```

- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageFireHazard`  

```csharp
private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageFireHazard;
```

- `private Game.UI.InGame.FireAndRescueInfoviewUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.FireAndRescueInfoviewUISystem+TypeHandle __TypeHandle;
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

- `public FireAndRescueInfoviewUISystem()`  

```csharp
public FireAndRescueInfoviewUISystem();
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


## Nested types

- `Game.UI.InGame.FireAndRescueInfoviewUISystem+FireHazardJob`  
- `Game.UI.InGame.FireAndRescueInfoviewUISystem+TypeHandle`  

