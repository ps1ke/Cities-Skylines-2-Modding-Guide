# Game.Simulation.ResourceBuyerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ResourceBuyerSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_BuyerQuery;
    private Unity.Entities.EntityQuery m_CarPrefabQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityQuery m_ResidentPrefabQuery;
    private Unity.Entities.EntityQuery m_PopulationQuery;
    private Unity.Entities.ComponentTypeSet m_PathfindTypes;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.TaxSystem m_TaxSystem;
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Prefabs.PersonalCarSelectData m_PersonalCarSelectData;
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Collections.NativeQueue<Game.Simulation.ResourceBuyerSystem+SalesEvent> m_SalesQueue;
    private Game.Simulation.ResourceBuyerSystem+TypeHandle __TypeHandle;
    private static const System.Int32 UPDATE_INTERVAL;

    public ResourceBuyerSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnStopRunning();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_BuyerQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuyerQuery;
```

- `private Unity.Entities.EntityQuery m_CarPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_CarPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.EntityQuery m_ResidentPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_ResidentPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_PopulationQuery`  

```csharp
private Unity.Entities.EntityQuery m_PopulationQuery;
```

- `private Unity.Entities.ComponentTypeSet m_PathfindTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_PathfindTypes;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  

```csharp
private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.TaxSystem m_TaxSystem`  

```csharp
private Game.Simulation.TaxSystem m_TaxSystem;
```

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Prefabs.PersonalCarSelectData m_PersonalCarSelectData`  

```csharp
private Game.Prefabs.PersonalCarSelectData m_PersonalCarSelectData;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Collections.NativeQueue<Game.Simulation.ResourceBuyerSystem+SalesEvent> m_SalesQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.ResourceBuyerSystem+SalesEvent> m_SalesQueue;
```

- `private Game.Simulation.ResourceBuyerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ResourceBuyerSystem+TypeHandle __TypeHandle;
```

- `private static const System.Int32 UPDATE_INTERVAL`  

```csharp
private static const System.Int32 UPDATE_INTERVAL;
```


## Constructors

- `public ResourceBuyerSystem()`  

```csharp
public ResourceBuyerSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
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

- `protected virtual OnStopRunning() : System.Void`  

```csharp
protected virtual System.Void OnStopRunning();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Simulation.ResourceBuyerSystem+SaleFlags`  
- `Game.Simulation.ResourceBuyerSystem+SalesEvent`  
- `Game.Simulation.ResourceBuyerSystem+BuyJob`  
- `Game.Simulation.ResourceBuyerSystem+HandleBuyersJob`  
- `Game.Simulation.ResourceBuyerSystem+TypeHandle`  

