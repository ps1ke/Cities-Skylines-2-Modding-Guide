# Game.Debug.TerrainDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `FormerlySerializedAs`  

## Code

```csharp
public class TerrainDebugSystem : Game.GameSystemBase
{
    private Game.Debug.TerrainDebugSystem+DebugMode m_Mode;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Rendering.TerrainRenderSystem m_TerrainRenderSystem;

    public TerrainDebugSystem();

    private System.Void DrawCascades();
    private System.Void DrawDebug();
    private System.Void DrawRoads();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void RenderDebugUI();
}
```


## Fields

- `private Game.Debug.TerrainDebugSystem+DebugMode m_Mode`  

```csharp
private Game.Debug.TerrainDebugSystem+DebugMode m_Mode;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Rendering.TerrainRenderSystem m_TerrainRenderSystem`  

```csharp
private Game.Rendering.TerrainRenderSystem m_TerrainRenderSystem;
```


## Constructors

- `public TerrainDebugSystem()`  

```csharp
public TerrainDebugSystem();
```


## Methods

- `private DrawCascades() : System.Void`  

```csharp
private System.Void DrawCascades();
```

- `private DrawDebug() : System.Void`  

```csharp
private System.Void DrawDebug();
```

- `private DrawRoads() : System.Void`  

```csharp
private System.Void DrawRoads();
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

- `public RenderDebugUI() : System.Void`  

```csharp
public System.Void RenderDebugUI();
```


## Nested types

- `Game.Debug.TerrainDebugSystem+DebugViewMode`  
- `Game.Debug.TerrainDebugSystem+DebugMode`  

