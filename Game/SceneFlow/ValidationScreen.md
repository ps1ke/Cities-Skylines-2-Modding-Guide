# Game.SceneFlow.ValidationScreen

**Assembly:** `Game`  
**Namespace:** `Game.SceneFlow`  

**Type:** class public  

**Base:** `Game.SceneFlow.FullScreenOverlay`  
**Implements:** `Game.SceneFlow.IScreenState`  

## Code

```csharp
public class ValidationScreen : Game.SceneFlow.FullScreenOverlay, Game.SceneFlow.IScreenState
{
    protected Game.SceneFlow.OverlayScreen overlayScreen { protected get; }
    protected System.String continueDisplayProperty { protected get; }
    protected System.String cancelDisplayProperty { protected get; }
    protected System.Int32 cancelDisplayPriority { protected get; }

    public ValidationScreen();

    public virtual System.Threading.Tasks.Task Execute(Game.SceneFlow.GameManager manager, System.Threading.CancellationToken token);
}
```


## Properties

- `protected Game.SceneFlow.OverlayScreen overlayScreen { protected get }`  

```csharp
protected Game.SceneFlow.OverlayScreen overlayScreen { protected get; }
```

- `protected System.String continueDisplayProperty { protected get }`  

```csharp
protected System.String continueDisplayProperty { protected get; }
```

- `protected System.String cancelDisplayProperty { protected get }`  

```csharp
protected System.String cancelDisplayProperty { protected get; }
```

- `protected System.Int32 cancelDisplayPriority { protected get }`  

```csharp
protected System.Int32 cancelDisplayPriority { protected get; }
```


## Constructors

- `public ValidationScreen()`  

```csharp
public ValidationScreen();
```


## Methods

- `public virtual Execute(Game.SceneFlow.GameManager manager, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public override async Task Execute(GameManager manager, CancellationToken token)
	{
		using EnabledActionScoped continueAction = new EnabledActionScoped(manager, "Engagement", actionA, HandleScreenChange, continueDisplayProperty, continueDisplayPriority);
		using EnabledActionScoped cancelAction = new EnabledActionScoped(manager, "Engagement", actionB, HandleScreenChange, cancelDisplayProperty, cancelDisplayPriority);
		using (Game.Input.InputManager.instance.CreateOverlayBarrier("ValidationScreen"))
		{
			OverlayBindings overlayBindings = manager.userInterface.overlayBindings;
			using (overlayBindings.ActivateScreenScoped(overlayScreen))
			{
				Task<(bool ok, InputDevice device)> input = IScreenState.WaitForInput(continueAction, cancelAction, null, token);
				await input;
				if (input.IsCompletedSuccessfully)
				{
					if (input.Result.ok)
					{
						UnityEngine.Debug.Log("OK");
					}
					else
					{
						UnityEngine.Debug.Log("Cancel");
					}
				}
			}
		}
	}
```


## Nested types

- `Game.SceneFlow.ValidationScreen+<Execute>d__8`  

