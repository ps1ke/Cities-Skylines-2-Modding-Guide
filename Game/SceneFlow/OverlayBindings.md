# Game.SceneFlow.OverlayBindings

**Assembly:** `Game`  
**Namespace:** `Game.SceneFlow`  

**Type:** class public  

**Base:** `Colossal.UI.Binding.CompositeBinding`  
**Implements:** `Colossal.UI.Binding.IUpdateBinding`, `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IBindingRegistry`, `Colossal.UI.Binding.IBindingGroup`  

## Code

```csharp
public class OverlayBindings : Colossal.UI.Binding.CompositeBinding, Colossal.UI.Binding.IUpdateBinding, Colossal.UI.Binding.IBinding, Colossal.UI.Binding.IBindingRegistry, Colossal.UI.Binding.IBindingGroup
{
    private System.Action<Game.SceneFlow.OverlayScreen> onScreenActivated;
    private readonly Colossal.UI.Binding.ValueBinding<Game.SceneFlow.OverlayScreen> m_ActiveScreen;
    private readonly Colossal.UI.Binding.ValueBinding<System.Single[]> m_Progress;
    private readonly Colossal.UI.Binding.ValueBinding<System.String[]> m_HintMessages;
    private readonly Colossal.UI.Binding.ValueBinding<System.String[]> m_CorruptDataMessages;
    private readonly System.Collections.Generic.SortedSet<Game.SceneFlow.OverlayScreen> m_ActiveScreenList;
    private static const System.String kGroup;

    public Game.SceneFlow.OverlayScreen currentlyActiveScreen { get; }
    public System.String[] hintMessages { get; set; }
    public System.String[] corruptDataMessages { get; set; }

    public OverlayBindings();

    public System.Void ActivateScreen(Game.SceneFlow.OverlayScreen screen);
    public Game.SceneFlow.OverlayBindings+ScopedScreen ActivateScreenScoped(Game.SceneFlow.OverlayScreen screen);
    public System.Void DeactivateAllScreens();
    public System.Void DeactivateScreen(Game.SceneFlow.OverlayScreen screen);
    public System.Single GetProgress(Game.SceneFlow.OverlayProgressType type);
    public System.Void SetProgress(Game.SceneFlow.OverlayProgressType type, System.Single progress);
    public System.Void SwapScreen(Game.SceneFlow.OverlayScreen screen1, Game.SceneFlow.OverlayScreen screen2);
    private System.Void UpdateScreen();
}
```


## Fields

- `private System.Action<Game.SceneFlow.OverlayScreen> onScreenActivated`  

```csharp
private System.Action<Game.SceneFlow.OverlayScreen> onScreenActivated;
```

- `private readonly Colossal.UI.Binding.ValueBinding<Game.SceneFlow.OverlayScreen> m_ActiveScreen`  

```csharp
private readonly Colossal.UI.Binding.ValueBinding<Game.SceneFlow.OverlayScreen> m_ActiveScreen;
```

- `private readonly Colossal.UI.Binding.ValueBinding<System.Single[]> m_Progress`  

```csharp
private readonly Colossal.UI.Binding.ValueBinding<System.Single[]> m_Progress;
```

- `private readonly Colossal.UI.Binding.ValueBinding<System.String[]> m_HintMessages`  

```csharp
private readonly Colossal.UI.Binding.ValueBinding<System.String[]> m_HintMessages;
```

- `private readonly Colossal.UI.Binding.ValueBinding<System.String[]> m_CorruptDataMessages`  

```csharp
private readonly Colossal.UI.Binding.ValueBinding<System.String[]> m_CorruptDataMessages;
```

- `private readonly System.Collections.Generic.SortedSet<Game.SceneFlow.OverlayScreen> m_ActiveScreenList`  

```csharp
private readonly System.Collections.Generic.SortedSet<Game.SceneFlow.OverlayScreen> m_ActiveScreenList;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `public Game.SceneFlow.OverlayScreen currentlyActiveScreen { get }`  

```csharp
public Game.SceneFlow.OverlayScreen currentlyActiveScreen { get; }
```

- `public System.String[] hintMessages { get; set }`  

```csharp
public System.String[] hintMessages { get; set; }
```

- `public System.String[] corruptDataMessages { get; set }`  

```csharp
public System.String[] corruptDataMessages { get; set; }
```


## Constructors

- `public OverlayBindings()`  

```csharp
public OverlayBindings()
	{
		AddBinding(m_ActiveScreen = new ValueBinding<OverlayScreen>("overlay", "activeScreen", OverlayScreen.None, new DelegateWriter<OverlayScreen>(delegate(IJsonWriter writer, OverlayScreen value)
		{
			writer.Write((int)value);
		})));
		AddBinding(m_Progress = new ValueBinding<float[]>("overlay", "progress", new float[3], new ArrayWriter<float>()));
		AddBinding(m_HintMessages = new ValueBinding<string[]>("overlay", "hintMessages", Array.Empty<string>(), new ArrayWriter<string>()));
		AddBinding(m_CorruptDataMessages = new ValueBinding<string[]>("overlay", "corruptDataMessages", null, ValueWriters.Nullable(new ArrayWriter<string>())));
	}
```


## Methods

- `public ActivateScreen(Game.SceneFlow.OverlayScreen screen) : System.Void`  

```csharp
public void ActivateScreen(OverlayScreen screen)
	{
		m_ActiveScreenList.Add(screen);
		UpdateScreen();
	}
```

- `public ActivateScreenScoped(Game.SceneFlow.OverlayScreen screen) : Game.SceneFlow.OverlayBindings+ScopedScreen`  

```csharp
public ScopedScreen ActivateScreenScoped(OverlayScreen screen)
	{
		return new ScopedScreen(screen, this);
	}
```

- `public DeactivateAllScreens() : System.Void`  

```csharp
public void DeactivateAllScreens()
	{
		m_ActiveScreenList.Clear();
		UpdateScreen();
	}
```

- `public DeactivateScreen(Game.SceneFlow.OverlayScreen screen) : System.Void`  

```csharp
public void DeactivateScreen(OverlayScreen screen)
	{
		m_ActiveScreenList.Remove(screen);
		UpdateScreen();
	}
```

- `public GetProgress(Game.SceneFlow.OverlayProgressType type) : System.Single`  

```csharp
public float GetProgress(OverlayProgressType type)
	{
		return m_Progress.value[(int)type];
	}
```

- `public SetProgress(Game.SceneFlow.OverlayProgressType type, System.Single progress) : System.Void`  

```csharp
public void SetProgress(OverlayProgressType type, float progress)
	{
		if (m_Progress.value[(int)type] != progress)
		{
			m_Progress.value[(int)type] = progress;
			m_Progress.TriggerUpdate();
		}
	}
```

- `public SwapScreen(Game.SceneFlow.OverlayScreen screen1, Game.SceneFlow.OverlayScreen screen2) : System.Void`  

```csharp
public void SwapScreen(OverlayScreen screen1, OverlayScreen screen2)
	{
		DeactivateScreen(screen1);
		ActivateScreen(screen2);
	}
```

- `private UpdateScreen() : System.Void`  

```csharp
private void UpdateScreen()
	{
		OverlayScreen overlayScreen = m_ActiveScreenList.FirstOrDefault();
		m_ActiveScreen.Update(overlayScreen);
		CompositeBinding.log.DebugFormat("Screen changed to {0}", overlayScreen);
		this.onScreenActivated?.Invoke(overlayScreen);
	}
```


## Events

- `onScreenActivated` : `System.Action<Game.SceneFlow.OverlayScreen>`  

```csharp
public event System.Action<Game.SceneFlow.OverlayScreen> onScreenActivated;
```


## Nested types

- `Game.SceneFlow.OverlayBindings+ScopedScreen`  
- `Game.SceneFlow.OverlayBindings+<>c`  

