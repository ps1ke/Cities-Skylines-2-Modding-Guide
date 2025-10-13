# Game.Rendering.BuildingLotRenderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BuildingLotRenderSystem : Game.GameSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem;
    private Unity.Entities.EntityQuery m_LotQuery;
    private Unity.Entities.EntityQuery m_RenderingSettingsQuery;
    private Game.Rendering.BuildingLotRenderSystem+TypeHandle __TypeHandle;

    public BuildingLotRenderSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem`  

```csharp
private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem;
```

- `private Unity.Entities.EntityQuery m_LotQuery`  

```csharp
private Unity.Entities.EntityQuery m_LotQuery;
```

- `private Unity.Entities.EntityQuery m_RenderingSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_RenderingSettingsQuery;
```

- `private Game.Rendering.BuildingLotRenderSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.BuildingLotRenderSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public BuildingLotRenderSystem()`  

```csharp
public BuildingLotRenderSystem();
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

- `Game.Rendering.BuildingLotRenderSystem+BuildingLotRenderJob`  
- `Game.Rendering.BuildingLotRenderSystem+BuildingTerraformRenderJob`  
- `Game.Rendering.BuildingLotRenderSystem+TypeHandle`  

