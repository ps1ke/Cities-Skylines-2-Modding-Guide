# Game.SceneFlow.WaitScreen

**Assembly:** `Game`  
**Namespace:** `Game.SceneFlow`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class WaitScreen
{
    private static const Game.SceneFlow.OverlayScreen k_OverlayScreen;

    public WaitScreen();

    public System.Threading.Tasks.Task Execute(Game.SceneFlow.GameManager manager, System.Threading.CancellationToken token, System.Threading.Tasks.Task taskToWaitFor);
}
```


## Fields

- `private static const Game.SceneFlow.OverlayScreen k_OverlayScreen`  

```csharp
private static const Game.SceneFlow.OverlayScreen k_OverlayScreen;
```


## Constructors

- `public WaitScreen()`  

```csharp
public WaitScreen();
```


## Methods

- `public Execute(Game.SceneFlow.GameManager manager, System.Threading.CancellationToken token, System.Threading.Tasks.Task taskToWaitFor) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task Execute(Game.SceneFlow.GameManager manager, System.Threading.CancellationToken token, System.Threading.Tasks.Task taskToWaitFor);
```


## Nested types

- `Game.SceneFlow.WaitScreen+<Execute>d__1`  

