# Game.Rendering.AreaBorderRenderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AreaBorderRenderSystem : Game.GameSystemBase
{
    private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Unity.Entities.EntityQuery m_AreaBorderQuery;
    private Unity.Entities.EntityQuery m_RenderingSettingsQuery;
    private Game.Rendering.AreaBorderRenderSystem+TypeHandle __TypeHandle;

    public AreaBorderRenderSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem`  

```csharp
private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Unity.Entities.EntityQuery m_AreaBorderQuery`  

```csharp
private Unity.Entities.EntityQuery m_AreaBorderQuery;
```

- `private Unity.Entities.EntityQuery m_RenderingSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_RenderingSettingsQuery;
```

- `private Game.Rendering.AreaBorderRenderSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.AreaBorderRenderSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AreaBorderRenderSystem()`  

```csharp
public AreaBorderRenderSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Rendering.AreaBorderRenderSystem+Border`  
- `Game.Rendering.AreaBorderRenderSystem+AreaBorderRenderJob`  
- `Game.Rendering.AreaBorderRenderSystem+TypeHandle`  

