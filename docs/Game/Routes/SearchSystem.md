# Game.Routes.SearchSystem

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_UpdatedRoutesQuery`  
- `private Unity.Entities.EntityQuery m_AllRoutesQuery`  
- `private Colossal.Collections.NativeQuadTree<Game.Routes.RouteSearchItem, Game.Common.QuadTreeBoundsXZ> m_SearchTree`  
- `private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> m_ElementCount`  
- `private Unity.Jobs.JobHandle m_ReadDependencies`  
- `private Unity.Jobs.JobHandle m_WriteDependencies`  
- `private System.Boolean m_Loaded`  
- `private Game.Routes.SearchSystem+TypeHandle __TypeHandle`  

## Constructors

- `public SearchSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddSearchTreeReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `public AddSearchTreeWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `private GetLoaded() : System.Boolean`  
- `public GetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Colossal.Collections.NativeQuadTree<Game.Routes.RouteSearchItem, Game.Common.QuadTreeBoundsXZ>`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Routes.SearchSystem+UpdateSearchTreeJob`  
- `Game.Routes.SearchSystem+TypeHandle`  

