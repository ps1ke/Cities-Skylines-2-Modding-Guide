# Game.Areas.SearchSystem

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_UpdatedAreasQuery`  
- `private Unity.Entities.EntityQuery m_AllAreasQuery`  
- `private Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> m_SearchTree`  
- `private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> m_TriangleCount`  
- `private Unity.Jobs.JobHandle m_ReadDependencies`  
- `private Unity.Jobs.JobHandle m_WriteDependencies`  
- `private System.Boolean m_Loaded`  
- `private Game.Areas.SearchSystem+TypeHandle __TypeHandle`  

## Constructors

- `public SearchSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddSearchTreeReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `public AddSearchTreeWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `private GetLoaded() : System.Boolean`  
- `public GetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ>`  
- `public GetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies, Unity.Collections.NativeParallelHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& triangleCount) : Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ>`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Areas.SearchSystem+UpdateSearchTreeJob`  
- `Game.Areas.SearchSystem+TypeHandle`  

