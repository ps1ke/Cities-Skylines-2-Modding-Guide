# Game.Rendering.CityBoundaryMeshSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Areas.MapTileSystem m_MapTileSystem`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Areas.SearchSystem m_AreaSearchSystem`  
- `private Unity.Entities.EntityQuery m_UpdatedQuery`  
- `private Unity.Entities.EntityQuery m_MapTileQuery`  
- `private Unity.Entities.EntityQuery m_SettingsQuery`  
- `private UnityEngine.Mesh m_BoundaryMesh`  
- `private UnityEngine.Material m_BoundaryMaterial`  
- `private Unity.Jobs.JobHandle m_MeshDependencies`  
- `private Unity.Collections.NativeList<Unity.Mathematics.float3> m_Vertices`  
- `private Unity.Collections.NativeList<Unity.Mathematics.float2> m_UVs`  
- `private Unity.Collections.NativeList<UnityEngine.Color32> m_Colors`  
- `private Unity.Collections.NativeList<System.Int32> m_Indices`  
- `private Colossal.Collections.NativeValue<Colossal.Mathematics.Bounds3> m_Bounds`  
- `private System.Boolean m_Loaded`  
- `private Game.Rendering.CityBoundaryMeshSystem+TypeHandle __TypeHandle`  

## Constructors

- `public CityBoundaryMeshSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private Clear() : System.Void`  
- `private DestroyMesh() : System.Void`  
- `private DisposeMeshData() : System.Void`  
- `public GetBoundaryMesh(UnityEngine.Mesh& mesh, UnityEngine.Material& material) : System.Boolean`  
- `private GetLoaded() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Rendering.CityBoundaryMeshSystem+Boundary`  
- `Game.Rendering.CityBoundaryMeshSystem+FillBoundaryQueueJob`  
- `Game.Rendering.CityBoundaryMeshSystem+FillBoundaryMeshDataJob`  
- `Game.Rendering.CityBoundaryMeshSystem+TypeHandle`  

