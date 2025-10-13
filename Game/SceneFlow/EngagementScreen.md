# Game.SceneFlow.EngagementScreen

**Assembly:** `Game`  
**Namespace:** `Game.SceneFlow`  

**Type:** class public  

**Base:** `Game.SceneFlow.FullScreenOverlay`  
**Implements:** `Game.SceneFlow.IScreenState`  

## Code

```csharp
public class EngagementScreen : Game.SceneFlow.FullScreenOverlay, Game.SceneFlow.IScreenState
{
    protected Game.SceneFlow.OverlayScreen overlayScreen { protected get; }
    protected System.String actionA { protected get; }
    protected System.String continueDisplayProperty { protected get; }

    public EngagementScreen();

    public virtual System.Threading.Tasks.Task Execute(Game.SceneFlow.GameManager manager, System.Threading.CancellationToken token);
}
```


## Properties

- `protected Game.SceneFlow.OverlayScreen overlayScreen { protected get }`  

```csharp
protected Game.SceneFlow.OverlayScreen overlayScreen { protected get; }
```

- `protected System.String actionA { protected get }`  

```csharp
protected System.String actionA { protected get; }
```

- `protected System.String continueDisplayProperty { protected get }`  

```csharp
protected System.String continueDisplayProperty { protected get; }
```


## Constructors

- `public EngagementScreen()`  

```csharp
public EngagementScreen();
```


## Methods

- `public virtual Execute(Game.SceneFlow.GameManager manager, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public virtual System.Threading.Tasks.Task Execute(Game.SceneFlow.GameManager manager, System.Threading.CancellationToken token);
```


## Nested types

- `Game.SceneFlow.EngagementScreen+<>c__DisplayClass6_0`  
- `Game.SceneFlow.EngagementScreen+<Execute>d__6`  

