# Game.Simulation.GameModeNaturalResourcesAdjustSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem`  
- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  
- `private Unity.Entities.EntityQuery m_GameModeSettingQuery`  
- `public static readonly System.Int32 kUpdatesPerDay`  

## Constructors

- `public GameModeNaturalResourcesAdjustSystem()`  

## Methods

- `private BoostStartGameNaturalResources(System.Single boostMultiplier) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.GameModeNaturalResourcesAdjustSystem+BoostInitialNaturalResourcesJob`  
- `Game.Simulation.GameModeNaturalResourcesAdjustSystem+BoostInitialGroundWaterJob`  
- `Game.Simulation.GameModeNaturalResourcesAdjustSystem+RefillNaturalResourcesJob`  

