# Game.Rendering.AreaBufferSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AreaBufferSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Unity.Entities.EntityQuery m_SettingsQuery;
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.UI.NameSystem m_NameSystem;
    private Game.Rendering.AreaBufferSystem+AreaTypeData[] m_AreaTypeData;
    private Game.Areas.AreaType m_LastSelectionAreaType;
    private Unity.Entities.EntityQuery m_SelectionQuery;
    private System.Boolean m_Loaded;
    private System.Int32 m_AreaParameters;
    private System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.String> m_CachedLabels;
    private Game.Rendering.AreaBufferSystem+TypeHandle __TypeHandle;

    public AreaBufferSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Boolean GetAreaBuffer(Game.Areas.AreaType type, UnityEngine.ComputeBuffer& buffer, UnityEngine.Material& material, UnityEngine.Bounds& bounds);
    private System.Boolean GetLoaded();
    public System.Boolean GetNameMaterial(Game.Areas.AreaType type, System.Int32 subMeshIndex, UnityEngine.Material& material);
    public System.Boolean GetNameMesh(Game.Areas.AreaType type, UnityEngine.Mesh& mesh, System.Int32& subMeshCount);
    private Game.Rendering.AreaBufferSystem+AreaTypeData InitializeAreaData<T>();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    private System.Void OnDictionaryChanged();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
    private System.Void UpdateLabelVertices(Game.Rendering.AreaBufferSystem+AreaTypeData data, System.Boolean isLoaded);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_SettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_SettingsQuery;
```

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem`  

```csharp
private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.UI.NameSystem m_NameSystem`  

```csharp
private Game.UI.NameSystem m_NameSystem;
```

- `private Game.Rendering.AreaBufferSystem+AreaTypeData[] m_AreaTypeData`  

```csharp
private Game.Rendering.AreaBufferSystem+AreaTypeData[] m_AreaTypeData;
```

- `private Game.Areas.AreaType m_LastSelectionAreaType`  

```csharp
private Game.Areas.AreaType m_LastSelectionAreaType;
```

- `private Unity.Entities.EntityQuery m_SelectionQuery`  

```csharp
private Unity.Entities.EntityQuery m_SelectionQuery;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private System.Int32 m_AreaParameters`  

```csharp
private System.Int32 m_AreaParameters;
```

- `private System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.String> m_CachedLabels`  

```csharp
private System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.String> m_CachedLabels;
```

- `private Game.Rendering.AreaBufferSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.AreaBufferSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AreaBufferSystem()`  

```csharp
public AreaBufferSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public GetAreaBuffer(Game.Areas.AreaType type, UnityEngine.ComputeBuffer& buffer, UnityEngine.Material& material, UnityEngine.Bounds& bounds) : System.Boolean`  

```csharp
public System.Boolean GetAreaBuffer(Game.Areas.AreaType type, UnityEngine.ComputeBuffer& buffer, UnityEngine.Material& material, UnityEngine.Bounds& bounds);
```

- `private GetLoaded() : System.Boolean`  

```csharp
private System.Boolean GetLoaded();
```

- `public GetNameMaterial(Game.Areas.AreaType type, System.Int32 subMeshIndex, UnityEngine.Material& material) : System.Boolean`  

```csharp
public System.Boolean GetNameMaterial(Game.Areas.AreaType type, System.Int32 subMeshIndex, UnityEngine.Material& material);
```

- `public GetNameMesh(Game.Areas.AreaType type, UnityEngine.Mesh& mesh, System.Int32& subMeshCount) : System.Boolean`  

```csharp
public System.Boolean GetNameMesh(Game.Areas.AreaType type, UnityEngine.Mesh& mesh, System.Int32& subMeshCount);
```

- `private InitializeAreaData<T>() : Game.Rendering.AreaBufferSystem+AreaTypeData`  

```csharp
private Game.Rendering.AreaBufferSystem+AreaTypeData InitializeAreaData<T>();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `private OnDictionaryChanged() : System.Void`  

```csharp
private System.Void OnDictionaryChanged();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
```

- `private UpdateLabelVertices(Game.Rendering.AreaBufferSystem+AreaTypeData data, System.Boolean isLoaded) : System.Void`  

```csharp
private System.Void UpdateLabelVertices(Game.Rendering.AreaBufferSystem+AreaTypeData data, System.Boolean isLoaded);
```


## Nested types

- `Game.Rendering.AreaBufferSystem+AreaTriangleData`  
- `Game.Rendering.AreaBufferSystem+MaterialData`  
- `Game.Rendering.AreaBufferSystem+AreaTypeData`  
- `Game.Rendering.AreaBufferSystem+ChunkData`  
- `Game.Rendering.AreaBufferSystem+ResetChunkDataJob`  
- `Game.Rendering.AreaBufferSystem+FillMeshDataJob`  
- `Game.Rendering.AreaBufferSystem+CalculateBoundsJob`  
- `Game.Rendering.AreaBufferSystem+LabelVertexData`  
- `Game.Rendering.AreaBufferSystem+FillNameDataJob`  
- `Game.Rendering.AreaBufferSystem+TypeHandle`  

