# Game.SceneFlow.SplashScreenSequence

**Assembly:** `Game`  
**Namespace:** `Game.SceneFlow`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.SceneFlow.IScreenState`  

## Fields

- `private static const System.String kSkipSplashKeyAction`  

## Constructors

- `public SplashScreenSequence()`  

## Methods

- `internal static <Execute>g__HandleScreenChange|2_0(Game.SceneFlow.OverlayScreen screen) : System.Boolean`  
- `public Execute(Game.SceneFlow.GameManager manager, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `private GetSplashSequence() : System.Collections.Generic.IEnumerable<Game.SceneFlow.OverlayScreen>`  
- `private WaitForCompletion(System.TimeSpan delay, UnityEngine.InputSystem.InputAction anyKey, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

## Nested types

- `Game.SceneFlow.SplashScreenSequence+<Execute>d__2`  
- `Game.SceneFlow.SplashScreenSequence+<GetSplashSequence>d__3`  

