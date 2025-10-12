# Game.Tools.ObjectToolBaseSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class abstract public  

**Base:** `Game.Tools.ToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Fields

- `protected Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  
- `protected Game.Objects.SearchSystem m_ObjectSearchSystem`  
- `protected Game.Simulation.WaterSystem m_WaterSystem`  
- `protected Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Tools.ObjectToolBaseSystem+TypeHandle __TypeHandle`  

## Constructors

- `protected ObjectToolBaseSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected CreateDefinitions(Unity.Entities.Entity objectPrefab, Unity.Entities.Entity transformPrefab, Unity.Entities.Entity brushPrefab, Unity.Entities.Entity owner, Unity.Entities.Entity original, Unity.Entities.Entity laneEditor, Unity.Entities.Entity theme, Unity.Collections.NativeList<Game.Tools.ControlPoint> controlPoints, Unity.Collections.NativeReference<Game.Tools.ObjectToolBaseSystem+AttachmentData> attachmentPrefab, System.Boolean editorMode, System.Boolean lefthandTraffic, System.Boolean removing, System.Boolean stamping, System.Single brushSize, System.Single brushAngle, System.Single brushStrength, System.Single distance, System.Single deltaTime, Game.Common.RandomSeed randomSeed, Game.Tools.Snap snap, Game.Tools.AgeMask ageMask, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public static GetFirstNodeIndex(Unity.Entities.DynamicBuffer<Game.Prefabs.SubAreaNode> nodes, Unity.Mathematics.int2 range) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  

## Nested types

- `Game.Tools.ObjectToolBaseSystem+AttachmentData`  
- `Game.Tools.ObjectToolBaseSystem+CreateDefinitionsJob`  
- `Game.Tools.ObjectToolBaseSystem+TypeHandle`  

