# Game.Rendering.BrushRenderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BrushRenderSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_BrushQuery;
    private Unity.Entities.EntityQuery m_SettingsQuery;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private UnityEngine.Mesh m_Mesh;
    private UnityEngine.MaterialPropertyBlock m_Properties;
    private System.Int32 m_BrushTexture;
    private System.Int32 m_BrushOpacity;
    private Game.Rendering.BrushRenderSystem+TypeHandle __TypeHandle;

    public BrushRenderSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private UnityEngine.Mesh GetMesh();
    private UnityEngine.MaterialPropertyBlock GetProperties();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    private System.Void PreviewHeight(Game.Tools.Brush brush, Game.Prefabs.BrushPrefab prefab, Game.Prefabs.TerraformingType terraformingType);
    private System.Void Render(UnityEngine.Rendering.ScriptableRenderContext context, System.Collections.Generic.List<UnityEngine.Camera> cameras);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_BrushQuery`  

```csharp
private Unity.Entities.EntityQuery m_BrushQuery;
```

- `private Unity.Entities.EntityQuery m_SettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_SettingsQuery;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private UnityEngine.Mesh m_Mesh`  

```csharp
private UnityEngine.Mesh m_Mesh;
```

- `private UnityEngine.MaterialPropertyBlock m_Properties`  

```csharp
private UnityEngine.MaterialPropertyBlock m_Properties;
```

- `private System.Int32 m_BrushTexture`  

```csharp
private System.Int32 m_BrushTexture;
```

- `private System.Int32 m_BrushOpacity`  

```csharp
private System.Int32 m_BrushOpacity;
```

- `private Game.Rendering.BrushRenderSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.BrushRenderSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public BrushRenderSystem()`  

```csharp
public BrushRenderSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private GetMesh() : UnityEngine.Mesh`  

```csharp
private UnityEngine.Mesh GetMesh();
```

- `private GetProperties() : UnityEngine.MaterialPropertyBlock`  

```csharp
private UnityEngine.MaterialPropertyBlock GetProperties();
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private PreviewHeight(Game.Tools.Brush brush, Game.Prefabs.BrushPrefab prefab, Game.Prefabs.TerraformingType terraformingType) : System.Void`  

```csharp
private System.Void PreviewHeight(Game.Tools.Brush brush, Game.Prefabs.BrushPrefab prefab, Game.Prefabs.TerraformingType terraformingType);
```

- `private Render(UnityEngine.Rendering.ScriptableRenderContext context, System.Collections.Generic.List<UnityEngine.Camera> cameras) : System.Void`  

```csharp
private System.Void Render(UnityEngine.Rendering.ScriptableRenderContext context, System.Collections.Generic.List<UnityEngine.Camera> cameras);
```


## Nested types

- `Game.Rendering.BrushRenderSystem+TypeHandle`  

