# Game.SceneFlow.LoadingScreen

**Assembly:** `Game`  
**Namespace:** `Game.SceneFlow`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.SceneFlow.IScreenState`  

## Code

```csharp
public class LoadingScreen : Game.SceneFlow.IScreenState
{
    public LoadingScreen();

    internal static System.Boolean <Execute>g__Poll|0_0(System.Single[] progress);
    public System.Threading.Tasks.Task Execute(Game.SceneFlow.GameManager manager, System.Threading.CancellationToken token);
}
```


## Constructors

- `public LoadingScreen()`  

```csharp
public LoadingScreen();
```


## Methods

- `internal static <Execute>g__Poll|0_0(System.Single[] progress) : System.Boolean`  

```csharp
internal static System.Boolean <Execute>g__Poll|0_0(System.Single[] progress);
```

- `public Execute(Game.SceneFlow.GameManager manager, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task Execute(Game.SceneFlow.GameManager manager, System.Threading.CancellationToken token);
```


## Nested types

- `Game.SceneFlow.LoadingScreen+<>c`  
- `Game.SceneFlow.LoadingScreen+<Execute>d__0`  

