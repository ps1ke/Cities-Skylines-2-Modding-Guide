# Game.Simulation.TransportLineSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_LineQuery`  
- `private Unity.Entities.EntityArchetype m_VehicleRequestArchetype`  
- `private Unity.Collections.NativeArray<System.Single> m_MaxTransportSpeed`  
- `private Unity.Jobs.JobHandle m_MaxTransportSpeedDeps`  
- `private Game.Simulation.TimeSystem m_TimeSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  
- `private Game.Simulation.TransportLineSystem+TypeHandle __TypeHandle`  
- `public static const System.UInt32 UPDATE_INTERVAL`  

## Constructors

- `public TransportLineSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public static CalculateVehicleCount(System.Single vehicleInterval, System.Single lineDuration) : System.Int32`  
- `public static CalculateVehicleInterval(System.Single lineDuration, System.Int32 vehicleCount) : System.Single`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public GetMaxTransportSpeed(System.Single& maxPassengerTransportSpeed, System.Single& maxCargoTransportSpeed) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Simulation.TransportLineSystem+SortedVehicle`  
- `Game.Simulation.TransportLineSystem+VehicleAction`  
- `Game.Simulation.TransportLineSystem+VehicleActionType`  
- `Game.Simulation.TransportLineSystem+TransportLineTickJob`  
- `Game.Simulation.TransportLineSystem+VehicleActionJob`  
- `Game.Simulation.TransportLineSystem+TypeHandle`  

