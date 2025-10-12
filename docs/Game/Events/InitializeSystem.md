# Game.Events.InitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  
- `private Unity.Entities.EntityQuery m_EventQuery`  
- `private Unity.Entities.EntityQuery m_InstanceQuery`  
- `private Unity.Entities.EntityQuery m_DisasterConfigQuery`  
- `private Unity.Entities.EntityQuery m_TargetQuery`  
- `private Unity.Entities.EntityQuery m_EDWSBuildingQuery`  
- `private Unity.Entities.EntityArchetype m_IgniteEventArchetype`  
- `private Unity.Entities.EntityArchetype m_ImpactEventArchetype`  
- `private Unity.Entities.EntityArchetype m_AccidentSiteEventArchetype`  
- `private Unity.Entities.EntityArchetype m_HealthEventArchetype`  
- `private Unity.Entities.EntityArchetype m_DamageEventArchetype`  
- `private Unity.Entities.EntityArchetype m_DestroyEventArchetype`  
- `private Unity.Entities.EntityArchetype m_SpectateEventArchetype`  
- `private Unity.Entities.EntityArchetype m_CriminalEventArchetype`  
- `private Game.Triggers.TriggerSystem m_TriggerSystem`  
- `private Unity.Entities.EntityCommandBuffer m_CommandBuffer`  
- `private Game.Events.InitializeSystem+TypeHandle __TypeHandle`  

## Constructors

- `public InitializeSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private AddRandomTarget(Unity.Entities.DynamicBuffer<Game.Events.TargetElement> targets, Game.Prefabs.EventTargetType targetType, Game.Prefabs.TransportType transportType) : System.Void`  
- `private CountInstances(Unity.Entities.Entity prefab) : System.Int32`  
- `private FindRandomLocation(Unity.Mathematics.Random& random) : Unity.Mathematics.float3`  
- `private GetCommandBuffer() : Unity.Entities.EntityCommandBuffer`  
- `private InitializeCalendarEvent(Unity.Entities.Entity eventEntity) : System.Void`  
- `private InitializeCrimeEvent(Unity.Entities.Entity eventEntity) : System.Void`  
- `private InitializeDestruction(Unity.Entities.Entity eventEntity) : System.Void`  
- `private InitializeFire(Unity.Entities.Entity eventEntity) : System.Void`  
- `private InitializeHealthEvent(Unity.Entities.Entity eventEntity) : System.Void`  
- `private InitializeMeetingEvent(Unity.Entities.Entity eventEntity) : System.Void`  
- `private InitializeSpectatorEvent(Unity.Entities.Entity eventEntity) : System.Void`  
- `private InitializeTrafficAccident(Unity.Entities.Entity eventEntity) : System.Void`  
- `private InitializeWaterLevelChangeEvent(Unity.Entities.Entity eventEntity) : System.Void`  
- `private InitializeWeatherEvent(Unity.Entities.Entity eventEntity) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Events.InitializeSystem+RandomEventTargetJob`  
- `Game.Events.InitializeSystem+TypeHandle`  

