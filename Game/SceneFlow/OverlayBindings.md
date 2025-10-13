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
public OverlayBindings();
```


## Methods

- `public ActivateScreen(Game.SceneFlow.OverlayScreen screen) : System.Void`  

```csharp
public System.Void ActivateScreen(Game.SceneFlow.OverlayScreen screen);
```

- `public ActivateScreenScoped(Game.SceneFlow.OverlayScreen screen) : Game.SceneFlow.OverlayBindings+ScopedScreen`  

```csharp
public Game.SceneFlow.OverlayBindings+ScopedScreen ActivateScreenScoped(Game.SceneFlow.OverlayScreen screen);
```

- `public DeactivateAllScreens() : System.Void`  

```csharp
public System.Void DeactivateAllScreens();
```

- `public DeactivateScreen(Game.SceneFlow.OverlayScreen screen) : System.Void`  

```csharp
public System.Void DeactivateScreen(Game.SceneFlow.OverlayScreen screen);
```

- `public GetProgress(Game.SceneFlow.OverlayProgressType type) : System.Single`  

```csharp
public System.Single GetProgress(Game.SceneFlow.OverlayProgressType type);
```

- `public SetProgress(Game.SceneFlow.OverlayProgressType type, System.Single progress) : System.Void`  

```csharp
public System.Void SetProgress(Game.SceneFlow.OverlayProgressType type, System.Single progress);
```

- `public SwapScreen(Game.SceneFlow.OverlayScreen screen1, Game.SceneFlow.OverlayScreen screen2) : System.Void`  

```csharp
public System.Void SwapScreen(Game.SceneFlow.OverlayScreen screen1, Game.SceneFlow.OverlayScreen screen2);
```

- `private UpdateScreen() : System.Void`  

```csharp
private System.Void UpdateScreen();
```


## Events

- `onScreenActivated` : `System.Action<Game.SceneFlow.OverlayScreen>`  

```csharp
public event System.Action<Game.SceneFlow.OverlayScreen> onScreenActivated;
```


## Nested types

- `Game.SceneFlow.OverlayBindings+ScopedScreen`  
- `Game.SceneFlow.OverlayBindings+<>c`  

