# Game.SceneFlow.ControllerDisconnectedScreen

**Assembly:** `Game`  
**Namespace:** `Game.SceneFlow`  

**Type:** class public  

**Base:** `Game.SceneFlow.FullScreenOverlay`  
**Implements:** `Game.SceneFlow.IScreenState`  

## Code

```csharp
public class ControllerDisconnectedScreen : Game.SceneFlow.FullScreenOverlay, Game.SceneFlow.IScreenState
{
    protected Game.SceneFlow.OverlayScreen overlayScreen { protected get; }
    protected System.String actionA { protected get; }
    protected System.String continueDisplayProperty { protected get; }

    public ControllerDisconnectedScreen();

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

- `public ControllerDisconnectedScreen()`  

```csharp
public ControllerDisconnectedScreen();
```


## Methods

- `public virtual Execute(Game.SceneFlow.GameManager manager, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public override async Task Execute(GameManager manager, CancellationToken token)
	{
		using EnabledActionScoped continueAction = new EnabledActionScoped(manager, "Engagement", actionA, HandleScreenChange, continueDisplayProperty, continueDisplayPriority);
		using (Game.Input.InputManager.instance.CreateOverlayBarrier("ControllerDisconnectedScreen"))
		{
			OverlayBindings overlayBindings = manager.userInterface.overlayBindings;
			using (overlayBindings.ActivateScreenScoped(overlayScreen))
			{
				while (!m_Done)
				{
					Task<(bool ok, InputDevice device)> input = IScreenState.WaitForInput(continueAction, null, m_CompletedEvent, token);
					Task<object> device = IScreenState.WaitForDevice(m_CompletedEvent, token);
					await Task.WhenAny(input, device);
					m_CompletedEvent?.Invoke();
					if (input.IsCompletedSuccessfully)
					{
						m_Done = await PlatformManager.instance.AssociateDevice(input.Result.device);
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
```


## Nested types

- `Game.SceneFlow.ControllerDisconnectedScreen+<Execute>d__6`  

