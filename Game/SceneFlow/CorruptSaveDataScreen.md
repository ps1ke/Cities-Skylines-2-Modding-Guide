# Game.SceneFlow.CorruptSaveDataScreen

**Assembly:** `Game`  
**Namespace:** `Game.SceneFlow`  

**Type:** class public  

**Base:** `Game.SceneFlow.FullScreenOverlay`  
**Implements:** `Game.SceneFlow.IScreenState`  

## Code

```csharp
public class CorruptSaveDataScreen : Game.SceneFlow.FullScreenOverlay, Game.SceneFlow.IScreenState
{
    protected Game.SceneFlow.OverlayScreen overlayScreen { protected get; }
    protected System.String actionA { protected get; }

    public CorruptSaveDataScreen();

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


## Constructors

- `public CorruptSaveDataScreen()`  

```csharp
public CorruptSaveDataScreen();
```


## Methods

- `public virtual Execute(Game.SceneFlow.GameManager manager, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public override async Task Execute(GameManager manager, CancellationToken token)
	{
		using EnabledActionScoped continueAction = new EnabledActionScoped(manager, "Engagement", actionA, HandleScreenChange, continueDisplayProperty, continueDisplayPriority);
		using (InputManager.instance.CreateOverlayBarrier("CorruptSaveDataScreen"))
		{
			OverlayBindings overlayBindings = manager.userInterface.overlayBindings;
			using (overlayBindings.ActivateScreenScoped(overlayScreen))
			{
				await IScreenState.WaitForInput(continueAction, null, null, token);
			}
		}
	}
```


## Nested types

- `Game.SceneFlow.CorruptSaveDataScreen+<Execute>d__4`  

