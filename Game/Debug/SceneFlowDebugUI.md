# Game.Debug.SceneFlowDebugUI

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `System.Object`  

**Attributes:** `DebugContainer`  

## Code

```csharp
public class SceneFlowDebugUI
{
    public SceneFlowDebugUI();

    private static System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildSceneFlowDebugUI();
}
```


## Constructors

- `public SceneFlowDebugUI()`  

```csharp
public SceneFlowDebugUI();
```


## Methods

- `private static BuildSceneFlowDebugUI() : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private static List<DebugUI.Widget> BuildSceneFlowDebugUI()
	{
		DebugUI.Foldout foldout = new DebugUI.Foldout();
		foldout.displayName = "Loaded Scenes + RootCount";
		for (int i = 0; i < SceneManager.sceneCount; i++)
		{
			Scene scene = SceneManager.GetSceneAt(i);
			foldout.children.Add(new DebugUI.Value
			{
				displayName = scene.name,
				getter = () => scene.rootCount
			});
		}
		DebugUI.Foldout foldout2 = new DebugUI.Foldout
		{
			displayName = "Crash tests"
		};
		foldout2.children.Add(new DebugUI.Button
		{
			displayName = "Exception",
			action = delegate
			{
				throw new Exception("Test exception");
			}
		});
		foldout2.children.Add(new DebugUI.Button
		{
			displayName = ForcedCrashCategory.AccessViolation.ToString(),
			action = delegate
			{
				Utils.ForceCrash(ForcedCrashCategory.AccessViolation);
			}
		});
		foldout2.children.Add(new DebugUI.Button
		{
			displayName = ForcedCrashCategory.Abort.ToString(),
			action = delegate
			{
				Utils.ForceCrash(ForcedCrashCategory.Abort);
			}
		});
		foldout2.children.Add(new DebugUI.Button
		{
			displayName = ForcedCrashCategory.FatalError.ToString(),
			action = delegate
			{
				Utils.ForceCrash(ForcedCrashCategory.FatalError);
			}
		});
		foldout2.children.Add(new DebugUI.Button
		{
			displayName = ForcedCrashCategory.MonoAbort.ToString(),
			action = delegate
			{
				Utils.ForceCrash(ForcedCrashCategory.MonoAbort);
			}
		});
		foldout2.children.Add(new DebugUI.Button
		{
			displayName = ForcedCrashCategory.PureVirtualFunction.ToString(),
			action = delegate
			{
				Utils.ForceCrash(ForcedCrashCategory.PureVirtualFunction);
			}
		});
		return new List<DebugUI.Widget>
		{
			new DebugUI.Value
			{
				displayName = "Mode",
				getter = () => GameManager.instance.gameMode
			},
			foldout2,
			foldout,
			new DebugUI.Button
			{
				displayName = "Refresh",
				action = delegate
				{
					DebugSystem.Rebuild(BuildSceneFlowDebugUI);
				}
			},
			new DebugUI.Button
			{
				displayName = "Dismiss all errors",
				action = delegate
				{
					ErrorDialogManager.DismissAllErrors();
				}
			}
		};
	}
```


## Nested types

- `Game.Debug.SceneFlowDebugUI+<>c`  
- `Game.Debug.SceneFlowDebugUI+<>c__DisplayClass0_0`  

