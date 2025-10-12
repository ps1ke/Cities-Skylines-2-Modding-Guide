# Game.Simulation.CountWorkplacesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_WorkplaceQuery`  
- `private Colossal.Collections.NativeAccumulator<Game.Companies.Workplaces> m_FreeWorkplaces`  
- `private Colossal.Collections.NativeAccumulator<Game.Companies.Workplaces> m_TotalWorkplaces`  
- `public Game.Companies.Workplaces m_LastFreeWorkplaces`  
- `public Game.Companies.Workplaces m_LastTotalWorkplaces`  
- `private Game.Simulation.CountWorkplacesSystem+TypeHandle __TypeHandle`  

## Constructors

- `public CountWorkplacesSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public GetFreeWorkplaces() : Game.Companies.Workplaces`  
- `public GetTotalWorkplaces() : Game.Companies.Workplaces`  
- `public GetUnemployedWorkspaceByLevel() : Game.Companies.Workplaces`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Simulation.CountWorkplacesSystem+CountWorkplacesJob`  
- `Game.Simulation.CountWorkplacesSystem+TypeHandle`  

