# Game.Simulation.WindSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.Wind>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

## Fields

- `public Game.Simulation.WindSimulationSystem m_WindSimulationSystem`  
- `public Game.Rendering.WindTextureSystem m_WindTextureSystem`  
- `public Game.Simulation.TerrainSystem m_TerrainSystem`  
- `public static readonly System.Int32 kTextureSize`  
- `public static readonly System.Int32 kUpdateInterval`  

## Properties

- `public Unity.Mathematics.int2 TextureSize { get }`  

## Constructors

- `public WindSystem()`  

## Methods

- `public virtual Deserialize<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public static GetWind(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.Wind> windMap) : Game.Simulation.Wind`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual SetDefaults(Colossal.Serialization.Entities.Context context) : Unity.Jobs.JobHandle`  

## Nested types

- `Game.Simulation.WindSystem+WindCopyJob`  

