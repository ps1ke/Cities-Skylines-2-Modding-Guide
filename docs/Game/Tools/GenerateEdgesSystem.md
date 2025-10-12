# Game.Tools.GenerateEdgesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Simulation.WaterSystem m_WaterSystem`  
- `private Game.Tools.GenerateObjectsSystem m_GenerateObjectsSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Common.ModificationBarrier2 m_TempEdgesBarrier`  
- `private Colossal.Collections.NativeValue<System.UInt32> m_BuildOrder`  
- `private Unity.Entities.EntityQuery m_CreatedEdgesQuery`  
- `private Unity.Entities.EntityQuery m_DefinitionQuery`  
- `private Unity.Entities.EntityQuery m_DeletedQuery`  
- `private Game.Tools.GenerateEdgesSystem+TypeHandle __TypeHandle`  

## Constructors

- `public GenerateEdgesSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public GetBuildOrder() : Colossal.Collections.NativeValue<System.UInt32>`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Tools.GenerateEdgesSystem+NodeMapKey`  
- `Game.Tools.GenerateEdgesSystem+LocalConnectItem`  
- `Game.Tools.GenerateEdgesSystem+OldEdgeKey`  
- `Game.Tools.GenerateEdgesSystem+CheckNodesJob`  
- `Game.Tools.GenerateEdgesSystem+FillOldEdgesJob`  
- `Game.Tools.GenerateEdgesSystem+CheckDefinitionsJob`  
- `Game.Tools.GenerateEdgesSystem+CollectLocalConnectItemsJob`  
- `Game.Tools.GenerateEdgesSystem+GenerateEdgesJob`  
- `Game.Tools.GenerateEdgesSystem+UpdateBuildOrderJob`  
- `Game.Tools.GenerateEdgesSystem+TypeHandle`  

