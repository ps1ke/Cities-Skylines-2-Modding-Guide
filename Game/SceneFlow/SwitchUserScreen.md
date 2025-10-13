# Game.SceneFlow.SwitchUserScreen

**Assembly:** `Game`  
**Namespace:** `Game.SceneFlow`  

**Type:** class public  

**Base:** `Game.SceneFlow.FullScreenOverlay`  
**Implements:** `Game.SceneFlow.IScreenState`  

## Code

```csharp
public class SwitchUserScreen : Game.SceneFlow.FullScreenOverlay, Game.SceneFlow.IScreenState
{
    protected Game.SceneFlow.OverlayScreen overlayScreen { protected get; }

    public SwitchUserScreen();

    public virtual System.Threading.Tasks.Task Execute(Game.SceneFlow.GameManager manager, System.Threading.CancellationToken token);
}
```


## Properties

- `protected Game.SceneFlow.OverlayScreen overlayScreen { protected get }`  

```csharp
protected Game.SceneFlow.OverlayScreen overlayScreen { protected get; }
```


## Constructors

- `public SwitchUserScreen()`  

```csharp
public SwitchUserScreen();
```


## Methods

- `public virtual Execute(Game.SceneFlow.GameManager manager, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public override async Task Execute(GameManager manager, CancellationToken token)
	{
		using (InputManager.instance.CreateOverlayBarrier("SwitchUserScreen"))
		{
			OverlayBindings overlayBindings = manager.userInterface.overlayBindings;
			using (overlayBindings.ActivateScreenScoped(overlayScreen))
			{
				await PlatformManager.instance.SignIn(SignInOptions.None, null);
			}
		}
	}
```


## Nested types

- `Game.SceneFlow.SwitchUserScreen+<Execute>d__2`  

