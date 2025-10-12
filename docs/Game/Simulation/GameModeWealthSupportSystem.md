# Game.Simulation.GameModeWealthSupportSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Unity.Entities.EntityQuery m_GameModeSettingQuery`  
- `private Unity.Entities.EntityQuery m_HouseholdGroup`  
- `private System.Int32 m_MinimumWealth`  
- `public static readonly System.Int32 kUpdatesPerDay`  

## Constructors

- `public GameModeWealthSupportSystem()`  

## Methods

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.GameModeWealthSupportSystem+SupportWageJob`  

