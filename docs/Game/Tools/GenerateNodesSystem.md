# Game.Tools.GenerateNodesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Net.SearchSystem m_SearchSystem`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Tools.GenerateObjectsSystem m_GenerateObjectsSystem`  
- `private Game.Common.ModificationBarrier1 m_ModificationBarrier`  
- `private Unity.Entities.EntityQuery m_DefinitionQuery`  
- `private Unity.Entities.EntityQuery m_DeletedQuery`  
- `private Game.Tools.GenerateNodesSystem+TypeHandle __TypeHandle`  

## Constructors

- `public GenerateNodesSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Tools.GenerateNodesSystem+UpdateData`  
- `Game.Tools.GenerateNodesSystem+NodeKey`  
- `Game.Tools.GenerateNodesSystem+DefinitionData`  
- `Game.Tools.GenerateNodesSystem+OldNodeKey`  
- `Game.Tools.GenerateNodesSystem+OldNodeValue`  
- `Game.Tools.GenerateNodesSystem+FillOldNodesJob`  
- `Game.Tools.GenerateNodesSystem+FillNodeMapJob`  
- `Game.Tools.GenerateNodesSystem+CollectUpdatesJob`  
- `Game.Tools.GenerateNodesSystem+CreateNodesJob`  
- `Game.Tools.GenerateNodesSystem+TypeHandle`  

