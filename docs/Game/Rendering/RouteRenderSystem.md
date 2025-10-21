# Game.Rendering.RouteRenderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RouteRenderSystem : Game.GameSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Rendering.RouteBufferSystem m_RouteBufferSystem;
    private Unity.Entities.EntityQuery m_RouteQuery;
    private Unity.Entities.EntityQuery m_LivePathQuery;
    private Unity.Entities.EntityQuery m_InfomodeQuery;
    private UnityEngine.Mesh m_Mesh;
    private UnityEngine.ComputeBuffer m_ArgsBuffer;
    private System.Collections.Generic.List<System.UInt32> m_ArgsArray;
    private System.Int32 m_RouteSegmentBuffer;
    private System.Int32 m_RouteColor;
    private System.Int32 m_RouteSize;
    private Game.Rendering.RouteRenderSystem+TypeHandle __TypeHandle;

    public RouteRenderSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void EnsureMesh();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    private System.Void Render(UnityEngine.Rendering.ScriptableRenderContext context, System.Collections.Generic.List<UnityEngine.Camera> cameras);
    private System.Boolean ShouldRenderRoutes();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Rendering.RouteBufferSystem m_RouteBufferSystem`  

```csharp
private Game.Rendering.RouteBufferSystem m_RouteBufferSystem;
```

- `private Unity.Entities.EntityQuery m_RouteQuery`  

```csharp
private Unity.Entities.EntityQuery m_RouteQuery;
```

- `private Unity.Entities.EntityQuery m_LivePathQuery`  

```csharp
private Unity.Entities.EntityQuery m_LivePathQuery;
```

- `private Unity.Entities.EntityQuery m_InfomodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_InfomodeQuery;
```

- `private UnityEngine.Mesh m_Mesh`  

```csharp
private UnityEngine.Mesh m_Mesh;
```

- `private UnityEngine.ComputeBuffer m_ArgsBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_ArgsBuffer;
```

- `private System.Collections.Generic.List<System.UInt32> m_ArgsArray`  

```csharp
private System.Collections.Generic.List<System.UInt32> m_ArgsArray;
```

- `private System.Int32 m_RouteSegmentBuffer`  

```csharp
private System.Int32 m_RouteSegmentBuffer;
```

- `private System.Int32 m_RouteColor`  

```csharp
private System.Int32 m_RouteColor;
```

- `private System.Int32 m_RouteSize`  

```csharp
private System.Int32 m_RouteSize;
```

- `private Game.Rendering.RouteRenderSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.RouteRenderSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public RouteRenderSystem()`  

```csharp
public RouteRenderSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private EnsureMesh() : System.Void`  

```csharp
private System.Void EnsureMesh();
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

- `private Render(UnityEngine.Rendering.ScriptableRenderContext context, System.Collections.Generic.List<UnityEngine.Camera> cameras) : System.Void`  

```csharp
private System.Void Render(UnityEngine.Rendering.ScriptableRenderContext context, System.Collections.Generic.List<UnityEngine.Camera> cameras);
```

- `private ShouldRenderRoutes() : System.Boolean`  

```csharp
private System.Boolean ShouldRenderRoutes();
```


## Nested types

- `Game.Rendering.RouteRenderSystem+TypeHandle`  

