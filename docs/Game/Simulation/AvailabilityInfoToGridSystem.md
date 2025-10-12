# Game.Simulation.AvailabilityInfoToGridSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.AvailabilityInfoCell>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Net.SearchSystem m_NetSearchSystem`  
- `private Game.Simulation.AvailabilityInfoToGridSystem+TypeHandle __TypeHandle`  
- `public static readonly System.Int32 kTextureSize`  
- `public static readonly System.Int32 kUpdatesPerDay`  

## Properties

- `public Unity.Mathematics.int2 TextureSize { get }`  

## Constructors

- `public AvailabilityInfoToGridSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public static GetAvailabilityInfo(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.AvailabilityInfoCell> AvailabilityInfoMap) : Game.Simulation.AvailabilityInfoCell`  
- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.AvailabilityInfoToGridSystem+NetIterator`  
- `Game.Simulation.AvailabilityInfoToGridSystem+AvailabilityInfoToGridJob`  
- `Game.Simulation.AvailabilityInfoToGridSystem+TypeHandle`  

