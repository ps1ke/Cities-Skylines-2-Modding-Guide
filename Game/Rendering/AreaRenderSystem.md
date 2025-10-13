# Game.Rendering.AreaRenderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class AreaRenderSystem : Game.GameSystemBase
{
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Rendering.AreaBufferSystem m_AreaBufferSystem;
    private Game.Rendering.AreaBatchSystem m_AreaBatchSystem;
    private Game.Rendering.CityBoundaryMeshSystem m_CityBoundaryMeshSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private System.Int32 m_AreaTriangleBuffer;
    private System.Int32 m_AreaBatchBuffer;
    private System.Int32 m_AreaBatchColors;
    private System.Int32 m_VisibleIndices;
    private UnityEngine.Mesh m_AreaMesh;
    private UnityEngine.GraphicsBuffer m_ArgsBuffer;
    private System.Collections.Generic.List<UnityEngine.GraphicsBuffer+IndirectDrawIndexedArgs> m_ArgsArray;

    public AreaRenderSystem();

    private static UnityEngine.Mesh CreateMesh();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    private System.Void Render(UnityEngine.Rendering.ScriptableRenderContext context, System.Collections.Generic.List<UnityEngine.Camera> cameras);
}
```


## Fields

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.Rendering.AreaBufferSystem m_AreaBufferSystem`  

```csharp
private Game.Rendering.AreaBufferSystem m_AreaBufferSystem;
```

- `private Game.Rendering.AreaBatchSystem m_AreaBatchSystem`  

```csharp
private Game.Rendering.AreaBatchSystem m_AreaBatchSystem;
```

- `private Game.Rendering.CityBoundaryMeshSystem m_CityBoundaryMeshSystem`  

```csharp
private Game.Rendering.CityBoundaryMeshSystem m_CityBoundaryMeshSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private System.Int32 m_AreaTriangleBuffer`  

```csharp
private System.Int32 m_AreaTriangleBuffer;
```

- `private System.Int32 m_AreaBatchBuffer`  

```csharp
private System.Int32 m_AreaBatchBuffer;
```

- `private System.Int32 m_AreaBatchColors`  

```csharp
private System.Int32 m_AreaBatchColors;
```

- `private System.Int32 m_VisibleIndices`  

```csharp
private System.Int32 m_VisibleIndices;
```

- `private UnityEngine.Mesh m_AreaMesh`  

```csharp
private UnityEngine.Mesh m_AreaMesh;
```

- `private UnityEngine.GraphicsBuffer m_ArgsBuffer`  

```csharp
private UnityEngine.GraphicsBuffer m_ArgsBuffer;
```

- `private System.Collections.Generic.List<UnityEngine.GraphicsBuffer+IndirectDrawIndexedArgs> m_ArgsArray`  

```csharp
private System.Collections.Generic.List<UnityEngine.GraphicsBuffer+IndirectDrawIndexedArgs> m_ArgsArray;
```


## Constructors

- `public AreaRenderSystem()`  

```csharp
public AreaRenderSystem();
```


## Methods

- `private static CreateMesh() : UnityEngine.Mesh`  

```csharp
private static UnityEngine.Mesh CreateMesh();
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

- `private Render(UnityEngine.Rendering.ScriptableRenderContext context, System.Collections.Generic.List<UnityEngine.Camera> cameras) : System.Void`  

```csharp
private System.Void Render(UnityEngine.Rendering.ScriptableRenderContext context, System.Collections.Generic.List<UnityEngine.Camera> cameras);
```


