# Game.SceneFlow.SplashScreenSequence

**Assembly:** `Game`  
**Namespace:** `Game.SceneFlow`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.SceneFlow.IScreenState`  

## Code

```csharp
public class SplashScreenSequence : Game.SceneFlow.IScreenState
{
    private static const System.String kSkipSplashKeyAction;

    public SplashScreenSequence();

    internal static System.Boolean <Execute>g__HandleScreenChange|2_0(Game.SceneFlow.OverlayScreen screen);
    public System.Threading.Tasks.Task Execute(Game.SceneFlow.GameManager manager, System.Threading.CancellationToken token);
    private System.Collections.Generic.IEnumerable<Game.SceneFlow.OverlayScreen> GetSplashSequence();
    private System.Threading.Tasks.Task WaitForCompletion(System.TimeSpan delay, UnityEngine.InputSystem.InputAction anyKey, System.Threading.CancellationToken token);
}
```


## Fields

- `private static const System.String kSkipSplashKeyAction`  

```csharp
private static const System.String kSkipSplashKeyAction;
```


## Constructors

- `public SplashScreenSequence()`  

```csharp
public SplashScreenSequence();
```


## Methods

- `internal static <Execute>g__HandleScreenChange|2_0(Game.SceneFlow.OverlayScreen screen) : System.Boolean`  

```csharp
internal static System.Boolean <Execute>g__HandleScreenChange|2_0(Game.SceneFlow.OverlayScreen screen);
```

- `public Execute(Game.SceneFlow.GameManager manager, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task Execute(Game.SceneFlow.GameManager manager, System.Threading.CancellationToken token);
```

- `private GetSplashSequence() : System.Collections.Generic.IEnumerable<Game.SceneFlow.OverlayScreen>`  

```csharp
private System.Collections.Generic.IEnumerable<Game.SceneFlow.OverlayScreen> GetSplashSequence();
```

- `private WaitForCompletion(System.TimeSpan delay, UnityEngine.InputSystem.InputAction anyKey, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
private System.Threading.Tasks.Task WaitForCompletion(System.TimeSpan delay, UnityEngine.InputSystem.InputAction anyKey, System.Threading.CancellationToken token);
```


## Nested types

- `Game.SceneFlow.SplashScreenSequence+<Execute>d__2`  
- `Game.SceneFlow.SplashScreenSequence+<GetSplashSequence>d__3`  

