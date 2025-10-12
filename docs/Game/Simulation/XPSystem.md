# Game.Simulation.XPSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.IXPSystem`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Collections.NativeQueue<Game.Simulation.XPMessage> m_XPMessages`  
- `private Unity.Collections.NativeQueue<Game.Simulation.XPGain> m_XPQueue`  
- `private Unity.Jobs.JobHandle m_QueueWriters`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.XPSystem+TypeHandle __TypeHandle`  

## Constructors

- `public XPSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddQueueWriter(Unity.Jobs.JobHandle handle) : System.Void`  
- `public GetQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.Simulation.XPGain>`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public TransferMessages(Game.Simulation.IXPMessageHandler handler) : System.Void`  

## Nested types

- `Game.Simulation.XPSystem+XPQueueProcessJob`  
- `Game.Simulation.XPSystem+TypeHandle`  

