# Game.Simulation.PropertyRenterSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem`  
- `private Unity.Entities.EntityQuery m_BuildingGroup`  
- `private Unity.Entities.EntityQuery m_GarbageFacilityGroup`  
- `private Unity.Entities.EntityQuery m_MovingAwayHouseholdGroup`  
- `private Unity.Entities.EntityArchetype m_RentEventArchetype`  
- `private Game.Simulation.PropertyRenterSystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_595560377_0`  
- `public static readonly System.Int32 kUpdatesPerDay`  

## Constructors

- `public PropertyRenterSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public static GetUpkeep(System.Int32 level, System.Single baseUpkeep, System.Int32 lotSize, Game.Zones.AreaType areaType, Game.Prefabs.EconomyParameterData& economyParameterData, System.Boolean isStorage = False) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

## Nested types

- `Game.Simulation.PropertyRenterSystem+PayRentJob`  
- `Game.Simulation.PropertyRenterSystem+RenterMovingAwayJob`  
- `Game.Simulation.PropertyRenterSystem+TypeHandle`  

