# Game.Simulation.CitizenTravelPurposeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CitizenTravelPurposeSystem : Game.GameSystemBase
{
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_ArrivedGroup;
    private Unity.Entities.EntityQuery m_StuckGroup;
    private Unity.Entities.EntityQuery m_EconomyParameterGroup;
    private Unity.Entities.EntityQuery m_OutsideConnectionQuery;
    private Unity.Entities.EntityQuery m_ServiceBuildingQuery;
    private Game.Simulation.CitizenTravelPurposeSystem+TypeHandle __TypeHandle;

    public CitizenTravelPurposeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_ArrivedGroup`  

```csharp
private Unity.Entities.EntityQuery m_ArrivedGroup;
```

- `private Unity.Entities.EntityQuery m_StuckGroup`  

```csharp
private Unity.Entities.EntityQuery m_StuckGroup;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterGroup`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterGroup;
```

- `private Unity.Entities.EntityQuery m_OutsideConnectionQuery`  

```csharp
private Unity.Entities.EntityQuery m_OutsideConnectionQuery;
```

- `private Unity.Entities.EntityQuery m_ServiceBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceBuildingQuery;
```

- `private Game.Simulation.CitizenTravelPurposeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CitizenTravelPurposeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CitizenTravelPurposeSystem()`  

```csharp
public CitizenTravelPurposeSystem();
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Simulation.CitizenTravelPurposeSystem+CitizenArriveJob`  
- `Game.Simulation.CitizenTravelPurposeSystem+Arrive`  
- `Game.Simulation.CitizenTravelPurposeSystem+ArriveType`  
- `Game.Simulation.CitizenTravelPurposeSystem+ArriveJob`  
- `Game.Simulation.CitizenTravelPurposeSystem+CitizenStuckJob`  
- `Game.Simulation.CitizenTravelPurposeSystem+TypeHandle`  

