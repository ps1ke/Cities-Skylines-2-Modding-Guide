# Game.Prefabs.RenderPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.RenderPrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Fields

- `private Colossal.IO.AssetDatabase.AssetReference<Colossal.IO.AssetDatabase.GeometryAsset> m_GeometryAsset`  
- `private Colossal.IO.AssetDatabase.AssetReference<Colossal.IO.AssetDatabase.SurfaceAsset>[] m_SurfaceAssets`  
- `private Colossal.Mathematics.Bounds3 m_Bounds`  
- `private System.Single m_SurfaceArea`  
- `private System.Int32 m_IndexCount`  
- `private System.Int32 m_VertexCount`  
- `private System.Int32 m_MeshCount`  
- `private System.Boolean m_IsImpostor`  
- `private System.Boolean m_ManualVTRequired`  
- `private UnityEngine.Material[] m_MaterialsContainer`  

## Properties

- `public System.Boolean hasGeometryAsset { get }`  
- `public Colossal.IO.AssetDatabase.GeometryAsset geometryAsset { get; set }`  
- `public System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SurfaceAsset> surfaceAssets { get; set }`  
- `public Colossal.Mathematics.Bounds3 bounds { get; set }`  
- `public System.Single surfaceArea { get; set }`  
- `public System.Int32 indexCount { get; set }`  
- `public System.Int32 vertexCount { get; set }`  
- `public System.Int32 meshCount { get; set }`  
- `public System.Boolean isImpostor { get; set }`  
- `public System.Boolean manualVTRequired { get; set }`  
- `public System.Int32 materialCount { get }`  

## Constructors

- `public RenderPrefab()`  

## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public GetSurfaceAsset(System.Int32 index) : Colossal.IO.AssetDatabase.SurfaceAsset`  
- `public ObtainMaterial(System.Int32 i, System.Boolean useVT = True) : UnityEngine.Material`  
- `public ObtainMaterials(System.Boolean useVT = True) : UnityEngine.Material[]`  
- `public ObtainMesh(System.Int32 materialIndex, System.Int32& subMeshIndex) : UnityEngine.Mesh`  
- `public ObtainMeshes() : UnityEngine.Mesh[]`  
- `public Release() : System.Void`  
- `public ReleaseMaterials() : System.Void`  
- `public ReleaseMeshes() : System.Void`  
- `public SetSurfaceAsset(System.Int32 index, Colossal.IO.AssetDatabase.SurfaceAsset value) : System.Void`  

## Nested types

- `Game.Prefabs.RenderPrefab+<>c`  

