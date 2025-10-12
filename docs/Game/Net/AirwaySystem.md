# Game.Net.AirwaySystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Serialization.LoadGameSystem m_LoadGameSystem`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Simulation.WaterSystem m_WaterSystem`  
- `private Unity.Entities.EntityQuery m_PrefabQuery`  
- `private Unity.Entities.EntityQuery m_AirplaneConnectionQuery`  
- `private Unity.Entities.EntityQuery m_OldConnectionQuery`  
- `private Game.Net.AirwayHelpers+AirwayData m_AirwayData`  
- `private Game.Net.AirwaySystem+TypeHandle __TypeHandle`  
- `private static const System.Single TERRAIN_SIZE`  
- `private static const System.Int32 HELICOPTER_GRID_WIDTH`  
- `private static const System.Int32 HELICOPTER_GRID_LENGTH`  
- `private static const System.Single HELICOPTER_CELL_SIZE`  
- `private static const System.Single HELICOPTER_PATH_HEIGHT`  
- `private static const System.Int32 AIRPLANE_GRID_WIDTH`  
- `private static const System.Int32 AIRPLANE_GRID_LENGTH`  
- `private static const System.Single AIRPLANE_CELL_SIZE`  
- `private static const System.Single AIRPLANE_PATH_HEIGHT`  

## Constructors

- `public AirwaySystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public Deserialize<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public GetAirwayData() : Game.Net.AirwayHelpers+AirwayData`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public Serialize<TWriter>(Colossal.Serialization.Entities.EntityWriterData writerData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : Unity.Jobs.JobHandle`  

## Nested types

- `Game.Net.AirwaySystem+SerializeJob<TWriter>`  
- `Game.Net.AirwaySystem+DeserializeJob<TReader>`  
- `Game.Net.AirwaySystem+SetDefaultsJob`  
- `Game.Net.AirwaySystem+GenerateAirwayLanesJob`  
- `Game.Net.AirwaySystem+TypeHandle`  

