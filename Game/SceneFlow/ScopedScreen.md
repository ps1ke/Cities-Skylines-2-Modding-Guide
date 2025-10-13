# Game.SceneFlow.OverlayBindings+ScopedScreen

**Assembly:** `Game`  
**Namespace:** `Game.SceneFlow`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public sealed struct ScopedScreen : System.IDisposable
{
    private Game.SceneFlow.OverlayBindings bindings;
    private Game.SceneFlow.OverlayScreen screen;

    public ScopedScreen(Game.SceneFlow.OverlayScreen screen, Game.SceneFlow.OverlayBindings bindings);

    public System.Void Dispose();
}
```


## Fields

- `private Game.SceneFlow.OverlayBindings bindings`  

```csharp
private Game.SceneFlow.OverlayBindings bindings;
```

- `private Game.SceneFlow.OverlayScreen screen`  

```csharp
private Game.SceneFlow.OverlayScreen screen;
```


## Constructors

- `public ScopedScreen(Game.SceneFlow.OverlayScreen screen, Game.SceneFlow.OverlayBindings bindings)`  

```csharp
public ScopedScreen(Game.SceneFlow.OverlayScreen screen, Game.SceneFlow.OverlayBindings bindings);
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```


