# Game.Rendering.TerrainMaterialSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `FormerlySerializedAs`, `CompilerGenerated`  

## Fields

- `private Colossal.Logging.ILog log`  
- `private System.Single m_TerrainVTBorder`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Rendering.WaterRenderSystem m_WaterRenderSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Simulation.SnowSystem m_SnowSystem`  
- `private UnityEngine.Material m_SplatMaterial`  
- `private UnityEngine.MaterialPropertyBlock m_Properties`  
- `private UnityEngine.Mesh m_BlitMesh`  
- `private UnityEngine.RenderTexture m_SplatMap`  
- `private UnityEngine.RenderTexture m_SplatWorldMap`  
- `private UnityEngine.Rendering.CommandBuffer m_CommandBuffer`  
- `private UnityEngine.Texture2D m_Noise`  
- `private System.Int32 m_UpdateIndex`  
- `private System.Int32 m_UpdateTick`  
- `private System.Boolean m_ForceUpdateWholeSplatmap`  
- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_MaterialPrefabs`  
- `private static readonly Unity.Mathematics.float4 kClearViewport`  
- `private static const System.Int32 m_SplatUpdateSize`  
- `private static const System.Int32 m_SplatRegularUpdateTick`  

## Properties

- `private UnityEngine.Material splatMaterial { private get; private set }`  
- `public UnityEngine.Texture splatmap { get }`  

## Constructors

- `public TerrainMaterialSystem()`  

## Methods

- `private CreateNoiseTexture() : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public ForceUpdateWholeSplatmap() : System.Void`  
- `public GetOrAddMaterialIndex(Unity.Entities.Entity prefab) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PatchReferences(Game.Serialization.PrefabReferences& references) : System.Void`  
- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  
- `public UpdateMaterial(UnityEngine.Material material) : System.Void`  
- `private UpdateSplatmap(UnityEngine.Rendering.CommandBuffer cmd, Unity.Mathematics.float4 viewport, System.Boolean bWorldUpdate) : System.Void`  

## Nested types

- `Game.Rendering.TerrainMaterialSystem+ShaderID`  

