# Game.Simulation.DispatchWaterSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem`  
- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  
- `private Unity.Entities.EntityQuery m_ConsumerQuery`  
- `private System.Boolean <freshConsumptionDisabled>k__BackingField`  
- `private System.Boolean <sewageConsumptionDisabled>k__BackingField`  
- `private Game.Simulation.DispatchWaterSystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_1010455350_0`  
- `private Unity.Entities.EntityQuery __query_1010455350_1`  
- `public static readonly System.Int16 kAlertCooldown`  
- `public static readonly System.Int16 kHealthPenaltyCooldown`  
- `private static const System.Single kNotificationMaxDelay`  

## Properties

- `public System.Boolean freshConsumptionDisabled { get; set }`  
- `public System.Boolean sewageConsumptionDisabled { get; set }`  

## Constructors

- `public DispatchWaterSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.DispatchWaterSystem+DispatchWaterJob`  
- `Game.Simulation.DispatchWaterSystem+TypeHandle`  

