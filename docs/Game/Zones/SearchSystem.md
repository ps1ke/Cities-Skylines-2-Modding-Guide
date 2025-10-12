# Game.Zones.SearchSystem

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_UpdatedBlocksQuery`  
- `private Unity.Entities.EntityQuery m_AllBlocksQuery`  
- `private Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Colossal.Mathematics.Bounds2> m_SearchTree`  
- `private Unity.Jobs.JobHandle m_ReadDependencies`  
- `private Unity.Jobs.JobHandle m_WriteDependencies`  
- `private System.Boolean m_Loaded`  
- `private Game.Zones.SearchSystem+TypeHandle __TypeHandle`  

## Constructors

- `public SearchSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddSearchTreeReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `public AddSearchTreeWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `private GetLoaded() : System.Boolean`  
- `public GetSearchTree(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Colossal.Mathematics.Bounds2>`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Zones.SearchSystem+UpdateSearchTreeJob`  
- `Game.Zones.SearchSystem+TypeHandle`  

