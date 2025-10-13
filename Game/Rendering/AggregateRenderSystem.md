# Game.Rendering.AggregateRenderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class AggregateRenderSystem : Game.GameSystemBase
{
    private Game.Rendering.AggregateMeshSystem m_AggregateMeshSystem;
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Tools.ToolSystem m_ToolSystem;

    public AggregateRenderSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    private System.Void Render(UnityEngine.Rendering.ScriptableRenderContext context, System.Collections.Generic.List<UnityEngine.Camera> cameras);
}
```


## Fields

- `private Game.Rendering.AggregateMeshSystem m_AggregateMeshSystem`  

```csharp
private Game.Rendering.AggregateMeshSystem m_AggregateMeshSystem;
```

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```


## Constructors

- `public AggregateRenderSystem()`  

```csharp
public AggregateRenderSystem();
```


## Methods

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


