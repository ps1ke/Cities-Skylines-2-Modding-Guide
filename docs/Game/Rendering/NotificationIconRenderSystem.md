# Game.Rendering.NotificationIconRenderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NotificationIconRenderSystem : Game.GameSystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Rendering.NotificationIconBufferSystem m_BufferSystem;
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private UnityEngine.Mesh m_Mesh;
    private UnityEngine.Material m_Material;
    private UnityEngine.ComputeBuffer m_ArgsBuffer;
    private UnityEngine.ComputeBuffer m_InstanceBuffer;
    private UnityEngine.Texture2DArray m_TextureArray;
    private System.UInt32[] m_ArgsArray;
    private Unity.Entities.EntityQuery m_ConfigurationQuery;
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private System.Int32 m_InstanceBufferID;
    private System.Boolean m_UpdateBuffer;
    private Game.Rendering.NotificationIconRenderSystem+TypeHandle __TypeHandle;

    public NotificationIconRenderSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void DisplayDataUpdated();
    private UnityEngine.ComputeBuffer GetArgsBuffer();
    private UnityEngine.ComputeBuffer GetInstanceBuffer(System.Int32 count);
    private UnityEngine.Material GetMaterial();
    private UnityEngine.Mesh GetMesh();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    private System.Void Render(UnityEngine.Rendering.ScriptableRenderContext context, System.Collections.Generic.List<UnityEngine.Camera> cameras);
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Rendering.NotificationIconBufferSystem m_BufferSystem`  

```csharp
private Game.Rendering.NotificationIconBufferSystem m_BufferSystem;
```

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private UnityEngine.Mesh m_Mesh`  

```csharp
private UnityEngine.Mesh m_Mesh;
```

- `private UnityEngine.Material m_Material`  

```csharp
private UnityEngine.Material m_Material;
```

- `private UnityEngine.ComputeBuffer m_ArgsBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_ArgsBuffer;
```

- `private UnityEngine.ComputeBuffer m_InstanceBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_InstanceBuffer;
```

- `private UnityEngine.Texture2DArray m_TextureArray`  

```csharp
private UnityEngine.Texture2DArray m_TextureArray;
```

- `private System.UInt32[] m_ArgsArray`  

```csharp
private System.UInt32[] m_ArgsArray;
```

- `private Unity.Entities.EntityQuery m_ConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigurationQuery;
```

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private System.Int32 m_InstanceBufferID`  

```csharp
private System.Int32 m_InstanceBufferID;
```

- `private System.Boolean m_UpdateBuffer`  

```csharp
private System.Boolean m_UpdateBuffer;
```

- `private Game.Rendering.NotificationIconRenderSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.NotificationIconRenderSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public NotificationIconRenderSystem()`  

```csharp
public NotificationIconRenderSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public DisplayDataUpdated() : System.Void`  

```csharp
public System.Void DisplayDataUpdated();
```

- `private GetArgsBuffer() : UnityEngine.ComputeBuffer`  

```csharp
private UnityEngine.ComputeBuffer GetArgsBuffer();
```

- `private GetInstanceBuffer(System.Int32 count) : UnityEngine.ComputeBuffer`  

```csharp
private UnityEngine.ComputeBuffer GetInstanceBuffer(System.Int32 count);
```

- `private GetMaterial() : UnityEngine.Material`  

```csharp
private UnityEngine.Material GetMaterial();
```

- `private GetMesh() : UnityEngine.Mesh`  

```csharp
private UnityEngine.Mesh GetMesh();
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


## Nested types

- `Game.Rendering.NotificationIconRenderSystem+TypeHandle`  

