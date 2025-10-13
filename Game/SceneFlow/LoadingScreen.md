# Game.SceneFlow.LoadingScreen

**Assembly:** `Game`  
**Namespace:** `Game.SceneFlow`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.SceneFlow.IScreenState`  

## Code

```csharp
public class LoadingScreen : Game.SceneFlow.IScreenState
{
    public LoadingScreen();

    internal static System.Boolean <Execute>g__Poll|0_0(System.Single[] progress);
    public System.Threading.Tasks.Task Execute(Game.SceneFlow.GameManager manager, System.Threading.CancellationToken token);
}
```


## Constructors

- `public LoadingScreen()`  

```csharp
public LoadingScreen();
```


## Methods

- `internal static <Execute>g__Poll|0_0(System.Single[] progress) : System.Boolean`  

```csharp
internal static System.Boolean <Execute>g__Poll|0_0(System.Single[] progress);
```

- `public Execute(Game.SceneFlow.GameManager manager, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public async Task Execute(GameManager manager, CancellationToken token)
	{
		OverlayBindings overlay = manager.userInterface.overlayBindings;
		float[] progress = new float[3];
		using (InputManager.instance.CreateOverlayBarrier("LoadingScreen"))
		{
			using (overlay.ActivateScreenScoped(OverlayScreen.Loading))
			{
				while (Poll(progress))
				{
					token.ThrowIfCancellationRequested();
					overlay.SetProgress(OverlayProgressType.Outer, progress[0]);
					overlay.SetProgress(OverlayProgressType.Middle, progress[1]);
					overlay.SetProgress(OverlayProgressType.Inner, progress[2]);
					await Task.Delay(100, token);
				}
				overlay.SetProgress(OverlayProgressType.Outer, 1f);
				overlay.SetProgress(OverlayProgressType.Middle, 1f);
				overlay.SetProgress(OverlayProgressType.Inner, 1f);
				int i = 0;
				while (i < 30)
				{
					token.ThrowIfCancellationRequested();
					await Task.Yield();
					int num = i + 1;
					i = num;
				}
			}
		}
		static bool Poll(float[] array)
		{
			array[0] = TaskManager.instance.GetTaskProgress(ProgressTracker.Group.Group1);
			array[1] = TaskManager.instance.GetTaskProgress(ProgressTracker.Group.Group2);
			array[2] = TaskManager.instance.GetTaskProgress(ProgressTracker.Group.Group3);
			return array.Any((float p) => p < 1f);
		}
	}
```


## Nested types

- `Game.SceneFlow.LoadingScreen+<>c`  
- `Game.SceneFlow.LoadingScreen+<Execute>d__0`  

