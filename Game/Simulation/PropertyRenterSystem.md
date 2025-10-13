# Game.Simulation.PropertyRenterSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PropertyRenterSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem;
    private Unity.Entities.EntityQuery m_BuildingGroup;
    private Unity.Entities.EntityQuery m_GarbageFacilityGroup;
    private Unity.Entities.EntityQuery m_MovingAwayHouseholdGroup;
    private Unity.Entities.EntityArchetype m_RentEventArchetype;
    private Game.Simulation.PropertyRenterSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_595560377_0;
    public static readonly System.Int32 kUpdatesPerDay;

    public PropertyRenterSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void Deserialize<TReader>(TReader reader);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public static System.Int32 GetUpkeep(System.Int32 level, System.Single baseUpkeep, System.Int32 lotSize, Game.Zones.AreaType areaType, Game.Prefabs.EconomyParameterData& economyParameterData, System.Boolean isStorage);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem`  

```csharp
private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem;
```

- `private Unity.Entities.EntityQuery m_BuildingGroup`  

```csharp
private Unity.Entities.EntityQuery m_BuildingGroup;
```

- `private Unity.Entities.EntityQuery m_GarbageFacilityGroup`  

```csharp
private Unity.Entities.EntityQuery m_GarbageFacilityGroup;
```

- `private Unity.Entities.EntityQuery m_MovingAwayHouseholdGroup`  

```csharp
private Unity.Entities.EntityQuery m_MovingAwayHouseholdGroup;
```

- `private Unity.Entities.EntityArchetype m_RentEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_RentEventArchetype;
```

- `private Game.Simulation.PropertyRenterSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.PropertyRenterSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_595560377_0`  

```csharp
private Unity.Entities.EntityQuery __query_595560377_0;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public PropertyRenterSystem()`  

```csharp
public PropertyRenterSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `public static GetUpkeep(System.Int32 level, System.Single baseUpkeep, System.Int32 lotSize, Game.Zones.AreaType areaType, Game.Prefabs.EconomyParameterData& economyParameterData, System.Boolean isStorage = False) : System.Int32`  

```csharp
public static System.Int32 GetUpkeep(System.Int32 level, System.Single baseUpkeep, System.Int32 lotSize, Game.Zones.AreaType areaType, Game.Prefabs.EconomyParameterData& economyParameterData, System.Boolean isStorage);
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


## Nested types

- `Game.Simulation.PropertyRenterSystem+PayRentJob`  
- `Game.Simulation.PropertyRenterSystem+RenterMovingAwayJob`  
- `Game.Simulation.PropertyRenterSystem+TypeHandle`  

