# Game.SceneFlow.ControllerPairingScreen

**Assembly:** `Game`  
**Namespace:** `Game.SceneFlow`  

**Type:** class public  

**Base:** `Game.SceneFlow.FullScreenOverlay`  
**Implements:** `Game.SceneFlow.IScreenState`  

## Code

```csharp
public class ControllerPairingScreen : Game.SceneFlow.FullScreenOverlay, Game.SceneFlow.IScreenState
{
    protected Game.SceneFlow.OverlayScreen overlayScreen { protected get; }
    protected System.String continueDisplayProperty { protected get; }
    protected System.String cancelDisplayProperty { protected get; }
    protected System.Int32 cancelDisplayPriority { protected get; }

    public ControllerPairingScreen();

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

- `public ControllerPairingScreen()`  

```csharp
public ControllerPairingScreen();
```


## Methods

- `public virtual Execute(Game.SceneFlow.GameManager manager, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public override async Task Execute(GameManager manager, CancellationToken token)
	{
		using (EnabledActionScoped continueAction = new EnabledActionScoped(manager, "Engagement", actionA, HandleScreenChange, continueDisplayProperty, continueDisplayPriority))
		{
			using EnabledActionScoped cancelAction = new EnabledActionScoped(manager, "Engagement", actionB, HandleScreenChange, cancelDisplayProperty, cancelDisplayPriority);
			using (Game.Input.InputManager.instance.CreateOverlayBarrier("ControllerPairingScreen"))
			{
				OverlayBindings overlayBindings = manager.userInterface.overlayBindings;
				using (overlayBindings.ActivateScreenScoped(overlayScreen))
				{
					while (!m_Done)
					{
						Task<(bool ok, InputDevice device)> input = IScreenState.WaitForInput(continueAction, cancelAction, m_CompletedEvent, token);
						Task<object> device = IScreenState.WaitForDevice(m_CompletedEvent, token);
						await Task.WhenAny(input, device);
						m_CompletedEvent?.Invoke();
						if (input.IsCompletedSuccessfully)
						{
							if (input.Result.ok)
							{
								SignInFlags signInFlags = await PlatformManager.instance.SignIn(SignInOptions.None, UserChangingCallback);
								m_Done = signInFlags.HasFlag(SignInFlags.Success);
								if (signInFlags.HasFlag(SignInFlags.UserChanged) && manager.gameMode.IsGameOrEditor())
								{
									manager.MainMenu();
								}
							}
							else
							{
								m_Done = await PlatformManager.instance.AssociateDevice(input.Result.device);
							}
						}
						else if (device.IsCompletedSuccessfully)
						{
							m_Done = true;
						}
						else
						{
							m_Done = true;
						}
					}
				}
			}
		}
		void UserChangingCallback(Task signInTask)
		{
			new WaitScreen().Execute(manager, token, signInTask);
		}
	}
```


## Nested types

- `Game.SceneFlow.ControllerPairingScreen+<>c__DisplayClass8_0`  
- `Game.SceneFlow.ControllerPairingScreen+<Execute>d__8`  

