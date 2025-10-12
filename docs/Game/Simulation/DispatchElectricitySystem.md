# Game.Simulation.DispatchElectricitySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem`  
- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  
- `private Unity.Entities.EntityQuery m_ConsumerQuery`  
- `private Game.Simulation.DispatchElectricitySystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_2129007938_0`  
- `private Unity.Entities.EntityQuery __query_2129007938_1`  
- `public static readonly System.Int16 kAlertCooldown`  

## Constructors

- `public DispatchElectricitySystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.DispatchElectricitySystem+DispatchElectricityJob`  
- `Game.Simulation.DispatchElectricitySystem+TypeHandle`  

