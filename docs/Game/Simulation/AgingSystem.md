# Game.Simulation.AgingSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_HouseholdQuery`  
- `private Unity.Entities.EntityQuery m_TimeDataQuery`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `public Colossal.Collections.NativeValue<System.Int32> m_BecomeTeen`  
- `public Colossal.Collections.NativeValue<System.Int32> m_BecomeAdult`  
- `public Colossal.Collections.NativeValue<System.Int32> m_BecomeElder`  
- `public Colossal.NativeCounter m_BecomeTeenCounter`  
- `public Colossal.NativeCounter m_BecomeAdultCounter`  
- `public Colossal.NativeCounter m_BecomeElderCounter`  
- `private Game.Simulation.AgingSystem+TypeHandle __TypeHandle`  
- `public static readonly System.Int32 kUpdatesPerDay`  
- `public static System.Boolean s_DebugAgeAllCitizens`  

## Constructors

- `public AgingSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public static GetAdultAgeLimitInDays() : System.Int32`  
- `public static GetElderAgeLimitInDays() : System.Int32`  
- `public static GetTeenAgeLimitInDays() : System.Int32`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.AgingSystem+AgingJob`  
- `Game.Simulation.AgingSystem+TypeHandle`  

