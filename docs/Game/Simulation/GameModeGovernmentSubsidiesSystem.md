# Game.Simulation.GameModeGovernmentSubsidiesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.Int32 m_LastSubsidyCoverPerDay`  
- `private System.Int32 m_MonthlySubsidy`  
- `private Game.Simulation.ICityServiceBudgetSystem m_CityServiceBudgetSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Unity.Entities.EntityQuery m_GameModeSettingQuery`  
- `public static readonly System.Int32 kUpdatesPerDay`  

## Properties

- `public System.Int32 LastSubsidyCoverPerDay { get }`  
- `public System.Int32 monthlySubsidy { get }`  

## Constructors

- `public GameModeGovernmentSubsidiesSystem()`  

## Methods

- `public GetGovernmentSubsidiesEnabled() : System.Boolean`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

