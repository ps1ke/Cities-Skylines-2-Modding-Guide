# Game.Simulation.PopulationToGridSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.PopulationCell>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_ResidentialPropertyQuery`  
- `private Game.Simulation.PopulationToGridSystem+TypeHandle __TypeHandle`  
- `public static readonly System.Int32 kTextureSize`  
- `public static readonly System.Int32 kUpdatesPerDay`  

## Properties

- `public Unity.Mathematics.int2 TextureSize { get }`  

## Constructors

- `public PopulationToGridSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  
- `public static GetPopulation(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.PopulationCell> populationMap) : Game.Simulation.PopulationCell`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.PopulationToGridSystem+PopulationToGridJob`  
- `Game.Simulation.PopulationToGridSystem+TypeHandle`  

