# Game.Rendering.PreRenderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class PreRenderSystem : Game.GameSystemBase
{
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.UpdateSystem m_UpdateSystem;

    public PreRenderSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.UpdateSystem m_UpdateSystem`  

```csharp
private Game.UpdateSystem m_UpdateSystem;
```


## Constructors

- `public PreRenderSystem()`  

```csharp
public PreRenderSystem();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


