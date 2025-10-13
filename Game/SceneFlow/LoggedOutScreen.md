# Game.SceneFlow.LoggedOutScreen

**Assembly:** `Game`  
**Namespace:** `Game.SceneFlow`  

**Type:** class public  

**Base:** `Game.SceneFlow.FullScreenOverlay`  
**Implements:** `Game.SceneFlow.IScreenState`  

## Code

```csharp
public class LoggedOutScreen : Game.SceneFlow.FullScreenOverlay, Game.SceneFlow.IScreenState
{
    protected Game.SceneFlow.OverlayScreen overlayScreen { protected get; }
    protected System.String actionA { protected get; }
    protected System.String continueDisplayProperty { protected get; }

    public LoggedOutScreen();

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

- `public LoggedOutScreen()`  

```csharp
public LoggedOutScreen();
```


## Methods

- `public virtual Execute(Game.SceneFlow.GameManager manager, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public override async Task Execute(GameManager manager, CancellationToken token)
	{
		using (EnabledActionScoped continueAction = new EnabledActionScoped(manager, "Engagement", actionA, HandleScreenChange, continueDisplayProperty, continueDisplayPriority))
		{
			using (Game.Input.InputManager.instance.CreateOverlayBarrier("LoggedOutScreen"))
			{
				OverlayBindings overlayBindings = manager.userInterface.overlayBindings;
				using (overlayBindings.ActivateScreenScoped(OverlayScreen.UserLoggedOut))
				{
					while (!m_Done)
					{
						Task<(bool ok, InputDevice device)> input = IScreenState.WaitForInput(continueAction, null, m_CompletedEvent, token);
						Task<UserChangedFlags> user = IScreenState.WaitForUser(m_CompletedEvent, token);
						await Task.WhenAny(input, user);
						m_CompletedEvent?.Invoke();
						if (input.IsCompletedSuccessfully)
						{
							SignInFlags signInFlags = await PlatformManager.instance.SignIn(SignInOptions.None, UserChangingCallback);
							m_Done = signInFlags.HasFlag(SignInFlags.Success);
							if (signInFlags.HasFlag(SignInFlags.UserChanged) && manager.gameMode.IsGameOrEditor())
							{
								manager.MainMenu();
							}
						}
						else if (user.IsCompletedSuccessfully)
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

- `Game.SceneFlow.LoggedOutScreen+<>c__DisplayClass6_0`  
- `Game.SceneFlow.LoggedOutScreen+<Execute>d__6`  

