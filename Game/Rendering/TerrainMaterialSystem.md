# Game.Rendering.TerrainMaterialSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `FormerlySerializedAs`, `CompilerGenerated`  

## Code

```csharp
public class TerrainMaterialSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable, Game.Serialization.IPostDeserialize
{
    private Colossal.Logging.ILog log;
    private System.Single m_TerrainVTBorder;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Rendering.WaterRenderSystem m_WaterRenderSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Simulation.SnowSystem m_SnowSystem;
    private UnityEngine.Material m_SplatMaterial;
    private UnityEngine.MaterialPropertyBlock m_Properties;
    private UnityEngine.Mesh m_BlitMesh;
    private UnityEngine.RenderTexture m_SplatMap;
    private UnityEngine.RenderTexture m_SplatWorldMap;
    private UnityEngine.Rendering.CommandBuffer m_CommandBuffer;
    private UnityEngine.Texture2D m_Noise;
    private System.Int32 m_UpdateIndex;
    private System.Int32 m_UpdateTick;
    private System.Boolean m_ForceUpdateWholeSplatmap;
    private Unity.Collections.NativeList<Unity.Entities.Entity> m_MaterialPrefabs;
    private static readonly Unity.Mathematics.float4 kClearViewport;
    private static const System.Int32 m_SplatUpdateSize;
    private static const System.Int32 m_SplatRegularUpdateTick;

    private UnityEngine.Material splatMaterial { private get; private set; }
    public UnityEngine.Texture splatmap { get; }

    public TerrainMaterialSystem();

    private System.Void CreateNoiseTexture();
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void ForceUpdateWholeSplatmap();
    public System.Int32 GetOrAddMaterialIndex(Unity.Entities.Entity prefab);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PatchReferences(Game.Serialization.PrefabReferences& references);
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
    public System.Void UpdateMaterial(UnityEngine.Material material);
    private System.Void UpdateSplatmap(UnityEngine.Rendering.CommandBuffer cmd, Unity.Mathematics.float4 viewport, System.Boolean bWorldUpdate);
}
```


## Fields

- `private Colossal.Logging.ILog log`  

```csharp
private Colossal.Logging.ILog log;
```

- `private System.Single m_TerrainVTBorder`  

```csharp
private System.Single m_TerrainVTBorder;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Rendering.WaterRenderSystem m_WaterRenderSystem`  

```csharp
private Game.Rendering.WaterRenderSystem m_WaterRenderSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Simulation.SnowSystem m_SnowSystem`  

```csharp
private Game.Simulation.SnowSystem m_SnowSystem;
```

- `private UnityEngine.Material m_SplatMaterial`  

```csharp
private UnityEngine.Material m_SplatMaterial;
```

- `private UnityEngine.MaterialPropertyBlock m_Properties`  

```csharp
private UnityEngine.MaterialPropertyBlock m_Properties;
```

- `private UnityEngine.Mesh m_BlitMesh`  

```csharp
private UnityEngine.Mesh m_BlitMesh;
```

- `private UnityEngine.RenderTexture m_SplatMap`  

```csharp
private UnityEngine.RenderTexture m_SplatMap;
```

- `private UnityEngine.RenderTexture m_SplatWorldMap`  

```csharp
private UnityEngine.RenderTexture m_SplatWorldMap;
```

- `private UnityEngine.Rendering.CommandBuffer m_CommandBuffer`  

```csharp
private UnityEngine.Rendering.CommandBuffer m_CommandBuffer;
```

- `private UnityEngine.Texture2D m_Noise`  

```csharp
private UnityEngine.Texture2D m_Noise;
```

- `private System.Int32 m_UpdateIndex`  

```csharp
private System.Int32 m_UpdateIndex;
```

- `private System.Int32 m_UpdateTick`  

```csharp
private System.Int32 m_UpdateTick;
```

- `private System.Boolean m_ForceUpdateWholeSplatmap`  

```csharp
private System.Boolean m_ForceUpdateWholeSplatmap;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_MaterialPrefabs`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> m_MaterialPrefabs;
```

- `private static readonly Unity.Mathematics.float4 kClearViewport`  

```csharp
private static readonly Unity.Mathematics.float4 kClearViewport;
```

- `private static const System.Int32 m_SplatUpdateSize`  

```csharp
private static const System.Int32 m_SplatUpdateSize;
```

- `private static const System.Int32 m_SplatRegularUpdateTick`  

```csharp
private static const System.Int32 m_SplatRegularUpdateTick;
```


## Properties

- `private UnityEngine.Material splatMaterial { private get; private set }`  

```csharp
private UnityEngine.Material splatMaterial { private get; private set; }
```

- `public UnityEngine.Texture splatmap { get }`  

```csharp
public UnityEngine.Texture splatmap { get; }
```


## Constructors

- `public TerrainMaterialSystem()`  

```csharp
public TerrainMaterialSystem();
```


## Methods

- `private CreateNoiseTexture() : System.Void`  

```csharp
private System.Void CreateNoiseTexture();
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public ForceUpdateWholeSplatmap() : System.Void`  

```csharp
public System.Void ForceUpdateWholeSplatmap();
```

- `public GetOrAddMaterialIndex(Unity.Entities.Entity prefab) : System.Int32`  

```csharp
public System.Int32 GetOrAddMaterialIndex(Unity.Entities.Entity prefab);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public PatchReferences(Game.Serialization.PrefabReferences& references) : System.Void`  

```csharp
public System.Void PatchReferences(Game.Serialization.PrefabReferences& references);
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```

- `public UpdateMaterial(UnityEngine.Material material) : System.Void`  

```csharp
public System.Void UpdateMaterial(UnityEngine.Material material);
```

- `private UpdateSplatmap(UnityEngine.Rendering.CommandBuffer cmd, Unity.Mathematics.float4 viewport, System.Boolean bWorldUpdate) : System.Void`  

```csharp
private System.Void UpdateSplatmap(UnityEngine.Rendering.CommandBuffer cmd, Unity.Mathematics.float4 viewport, System.Boolean bWorldUpdate);
```


## Nested types

- `Game.Rendering.TerrainMaterialSystem+ShaderID`  

