# Game.Objects.SearchSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Unity.Entities.EntityQuery m_UpdatedStaticsQuery`  
- `private Unity.Entities.EntityQuery m_AllStaticsQuery`  
- `private Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_StaticSearchTree`  
- `private Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_MovingSearchTree`  
- `private Unity.Jobs.JobHandle m_StaticReadDependencies`  
- `private Unity.Jobs.JobHandle m_StaticWriteDependencies`  
- `private Unity.Jobs.JobHandle m_MovingReadDependencies`  
- `private Unity.Jobs.JobHandle m_MovingWriteDependencies`  
- `private System.Boolean m_Loaded`  
- `private Game.Objects.SearchSystem+TypeHandle __TypeHandle`  

## Constructors

- `public SearchSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddMovingSearchTreeReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `public AddMovingSearchTreeWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `public AddStaticSearchTreeReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `public AddStaticSearchTreeWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `private GetLoaded() : System.Boolean`  
- `public GetMovingSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`  
- `public GetStaticSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Objects.SearchSystem+UpdateSearchTreeJob`  
- `Game.Objects.SearchSystem+TypeHandle`  

