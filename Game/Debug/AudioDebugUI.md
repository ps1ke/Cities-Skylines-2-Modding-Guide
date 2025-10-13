# Game.Debug.AudioDebugUI

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `DebugContainer`  

## Code

```csharp
public static class AudioDebugUI
{
    internal static System.String <BuildAudioDebugUI>g__GetLoadedClips|0_0();
    internal static System.String <BuildAudioDebugUI>g__GetPlayingClips|0_1();
    private static System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildAudioDebugUI();
}
```


## Methods

- `internal static <BuildAudioDebugUI>g__GetLoadedClips|0_0() : System.String`  

```csharp
internal static System.String <BuildAudioDebugUI>g__GetLoadedClips|0_0();
```

- `internal static <BuildAudioDebugUI>g__GetPlayingClips|0_1() : System.String`  

```csharp
internal static System.String <BuildAudioDebugUI>g__GetPlayingClips|0_1();
```

- `private static BuildAudioDebugUI() : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private static List<DebugUI.Widget> BuildAudioDebugUI()
	{
		Radio radio = AudioManager.instance.radio;
		return new List<DebugUI.Widget>
		{
			new DebugUI.Container("Radio", new ObservableList<DebugUI.Widget>
			{
				new DebugUI.Value
				{
					displayName = "Current radio station",
					getter = () => radio?.currentChannel?.name
				},
				new DebugUI.Value
				{
					displayName = "Current program",
					getter = () => radio?.currentChannel?.currentProgram?.name
				},
				new DebugUI.Value
				{
					displayName = "Currently playing",
					getter = () => radio?.currentlyPlayingClipName ?? ""
				},
				new DebugUI.Value
				{
					displayName = "Source0 progress",
					getter = delegate
					{
						Radio radio2 = radio;
						return ((radio2 != null && radio2.GetActiveSource() == 0) ? "x " : "") + FormatUtils.FormatTimeMs(radio?.GetAudioSourceTimeElapsed(0) ?? 0.0) + "/" + FormatUtils.FormatTimeMs(radio?.GetAudioSourceDuration(0) ?? 0.0);
					}
				},
				new DebugUI.Value
				{
					displayName = "Source0 remaining",
					getter = delegate
					{
						Radio radio2 = radio;
						return ((radio2 != null && radio2.GetActiveSource() == 0) ? "x " : "") + FormatUtils.FormatTimeMs(radio?.GetAudioSourceTimeRemaining(0) ?? 0.0);
					}
				},
				new DebugUI.Value
				{
					displayName = "Source1 progress",
					getter = delegate
					{
						Radio radio2 = radio;
						return ((radio2 != null && radio2.GetActiveSource() == 1) ? "x " : "") + FormatUtils.FormatTimeMs(radio?.GetAudioSourceTimeElapsed(1) ?? 0.0) + "/" + FormatUtils.FormatTimeMs(radio?.GetAudioSourceDuration(1) ?? 0.0);
					}
				},
				new DebugUI.Value
				{
					displayName = "Source1 remaining",
					getter = delegate
					{
						Radio radio2 = radio;
						return ((radio2 != null && radio2.GetActiveSource() == 1) ? "x " : "") + FormatUtils.FormatTimeMs(radio?.GetAudioSourceTimeRemaining(1) ?? 0.0);
					}
				},
				new DebugUI.Value
				{
					displayName = "Next check",
					getter = () => radio?.nextTimeCheck - (double)Time.timeSinceLevelLoad
				},
				new DebugUI.Button
				{
					displayName = "Reload",
					action = delegate
					{
						radio?.Reload();
					}
				}
			}),
			new DebugUI.Container("Clips", new ObservableList<DebugUI.Widget>
			{
				new DebugUI.Value
				{
					displayName = "Loaded clips",
					getter = GetLoadedClips
				},
				new DebugUI.Value
				{
					displayName = "Playing clips",
					getter = GetPlayingClips
				}
			})
		};
		static string GetLoadedClips()
		{
			AudioManager.AudioSourcePool.Stats(out var loadedSize, out var maxLoadedSize, out var loadedCount, out var _, out var _);
			return $"{FormatUtils.FormatBytes(loadedSize)} / {FormatUtils.FormatBytes(maxLoadedSize)} ({loadedCount})";
		}
		static string GetPlayingClips()
		{
			AudioManager.AudioSourcePool.Stats(out var _, out var _, out var _, out var playingSize, out var playingCount);
			return $"{FormatUtils.FormatBytes(playingSize)} ({playingCount})";
		}
	}
```


## Nested types

- `Game.Debug.AudioDebugUI+<>c__DisplayClass0_0`  

