# Game.Simulation.GroundHeightSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Simulation.WaterSystem m_WaterSystem`  
- `private Game.Common.ModificationBarrier2 m_ModificationBarrier`  
- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  
- `private Game.Net.SearchSystem m_NetSearchSystem`  
- `private Game.Areas.SearchSystem m_AreaSearchSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Areas.GeometrySystem m_AreaGeometrySystem`  
- `private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_NewUpdates`  
- `private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_PendingUpdates`  
- `private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_ReadingUpdates`  
- `private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_ReadyUpdates`  
- `private Unity.Jobs.JobHandle m_UpdateDeps`  
- `private Game.Simulation.GroundHeightSystem+LoadHeightsState m_LoadHeightsState`  
- `private Game.Simulation.GroundHeightSystem+TypeHandle __TypeHandle`  

## Constructors

- `public GroundHeightSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AfterReadHeights() : System.Void`  
- `public BeforeReadHeights() : System.Void`  
- `public BeforeUpdateHeights() : System.Void`  
- `public Deserialize<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public GetUpdateBuffer() : Unity.Collections.NativeList<Colossal.Mathematics.Bounds2>`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public Serialize<TWriter>(Colossal.Serialization.Entities.EntityWriterData writerData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : Unity.Jobs.JobHandle`  

## Nested types

- `Game.Simulation.GroundHeightSystem+LoadHeightsState`  
- `Game.Simulation.GroundHeightSystem+SerializeJob<TWriter>`  
- `Game.Simulation.GroundHeightSystem+DeserializeJob<TReader>`  
- `Game.Simulation.GroundHeightSystem+SetDefaultsJob`  
- `Game.Simulation.GroundHeightSystem+BoundsFindJob`  
- `Game.Simulation.GroundHeightSystem+DequeueJob`  
- `Game.Simulation.GroundHeightSystem+UpdateHeightsJob`  
- `Game.Simulation.GroundHeightSystem+TypeHandle`  

