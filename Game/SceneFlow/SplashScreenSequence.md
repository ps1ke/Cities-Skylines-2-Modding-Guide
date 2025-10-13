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
public async Task Execute(GameManager manager, CancellationToken token)
	{
		using (EnabledActionScoped anyKey = new EnabledActionScoped(manager, "Splash screen", "Skip", HandleScreenChange))
		{
			using (Game.Input.InputManager.instance.CreateOverlayBarrier("SplashScreenSequence"))
			{
				OverlayBindings overlay = manager.userInterface.overlayBindings;
				OverlayScreen[] splashes = GetSplashSequence().ToArray();
				int i = 0;
				while (i < splashes.Length)
				{
					if (i == 0)
					{
						overlay.ActivateScreen(splashes[i]);
					}
					else
					{
						overlay.SwapScreen(splashes[i - 1], splashes[i]);
					}
					await WaitForCompletion(TimeSpan.FromSeconds(4.0), anyKey, token);
					overlay.DeactivateScreen(splashes[i]);
					token.ThrowIfCancellationRequested();
					int num = i + 1;
					i = num;
				}
				i = 0;
				while (i < 60)
				{
					await Task.Yield();
					int num = i + 1;
					i = num;
				}
			}
		}
		static bool HandleScreenChange(OverlayScreen screen)
		{
			switch (screen)
			{
			case OverlayScreen.Splash1:
			case OverlayScreen.Splash2:
			case OverlayScreen.Splash3:
			case OverlayScreen.Splash4:
			case OverlayScreen.PiracyDisclaimer:
			case OverlayScreen.PhotosensitivityDisclaimer:
				Game.Input.InputManager.instance.AssociateActionsWithUser(associate: false);
				break;
			case OverlayScreen.None:
			case OverlayScreen.Loading:
				Game.Input.InputManager.instance.AssociateActionsWithUser(associate: true);
				break;
			}
			if (screen != OverlayScreen.Splash1 && screen != OverlayScreen.Splash2 && screen != OverlayScreen.Splash3)
			{
				return screen == OverlayScreen.Splash4;
			}
			return true;
		}
	}
```

- `private GetSplashSequence() : System.Collections.Generic.IEnumerable<Game.SceneFlow.OverlayScreen>`  

```csharp
private IEnumerable<OverlayScreen> GetSplashSequence()
	{
		yield return OverlayScreen.Splash1;
		yield return OverlayScreen.Splash2;
		yield return OverlayScreen.Splash4;
	}
```

- `private WaitForCompletion(System.TimeSpan delay, UnityEngine.InputSystem.InputAction anyKey, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
private Task WaitForCompletion(TimeSpan delay, InputAction anyKey, CancellationToken token)
	{
		return Task.WhenAny(Task.Delay(delay, token), IScreenState.WaitForInput(anyKey, null, null, token));
	}
```


## Nested types

- `Game.SceneFlow.SplashScreenSequence+<Execute>d__2`  
- `Game.SceneFlow.SplashScreenSequence+<GetSplashSequence>d__3`  

