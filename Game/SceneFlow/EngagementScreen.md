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
public override async Task Execute(GameManager manager, CancellationToken token)
	{
		using (EnabledActionScoped continueAction = new EnabledActionScoped(manager, "Engagement", actionA, HandleScreenChange, continueDisplayProperty, continueDisplayPriority))
		{
			using (Game.Input.InputManager.instance.CreateOverlayBarrier("EngagementScreen"))
			{
				OverlayBindings overlayBindings = manager.userInterface.overlayBindings;
				using (overlayBindings.ActivateScreenScoped(overlayScreen))
				{
					while (!m_Done)
					{
						Task<(bool ok, InputDevice device)> input = IScreenState.WaitForInput(continueAction, null, m_CompletedEvent, token);
						await input;
						if (input.IsCompletedSuccessfully)
						{
							if (!PlatformManager.instance.isUserSignedIn)
							{
								m_Done = (await PlatformManager.instance.SignIn(SignInOptions.WithUI, UserChangingCallback)).HasFlag(SignInFlags.Success);
							}
							else
							{
								m_Done = await PlatformManager.instance.AssociateDevice(input.Result.device);
							}
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

- `Game.SceneFlow.EngagementScreen+<>c__DisplayClass6_0`  
- `Game.SceneFlow.EngagementScreen+<Execute>d__6`  

