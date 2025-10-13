# Game.UI.InputHintBindings

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `Colossal.UI.Binding.CompositeBinding`  
**Implements:** `Colossal.UI.Binding.IUpdateBinding`, `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IBindingRegistry`, `Colossal.UI.Binding.IBindingGroup`, `System.IDisposable`  

## Code

```csharp
public class InputHintBindings : Colossal.UI.Binding.CompositeBinding, Colossal.UI.Binding.IUpdateBinding, Colossal.UI.Binding.IBinding, Colossal.UI.Binding.IBindingRegistry, Colossal.UI.Binding.IBindingGroup, System.IDisposable
{
    private readonly Colossal.UI.Binding.ValueBinding<Game.UI.InputHintBindings+InputHint[]> m_ActiveHintsBinding;
    private readonly Colossal.UI.Binding.GetterMapBinding<Game.UI.InputHintBindings+InputHintQuery, Game.UI.InputHintBindings+InputHint> m_HintsMapBinding;
    private readonly Colossal.UI.Binding.ValueBinding<System.Int32> m_GamepadTypeBinding;
    private readonly Colossal.UI.Binding.GetterMapBinding<Game.UI.InputHintBindings+TutorialInputHintQuery, Game.UI.InputHintBindings+InputHint[]> m_TutorialHints;
    private System.Collections.Generic.Dictionary<System.ValueTuple<System.String, System.Int32>, Game.UI.InputHintBindings+InputHint> m_Hints;
    private System.Boolean m_HintsDirty;
    private System.Boolean m_TutorialHintsDirty;
    private System.Action<Game.Input.ProxyAction> onInputHintPerformed;
    private static readonly System.String[] axisControls;
    private static readonly System.String[] allDirs;
    private static readonly System.String[] horizontal;
    private static readonly System.String[] vertical;
    private static readonly System.String[] axes;
    private static System.Collections.Generic.Dictionary<System.Collections.Generic.IReadOnlyList<Game.Input.ProxyModifier>, System.Collections.Generic.List<Game.Input.ProxyBinding>> modifiersGroups;
    private static const System.String kGroup;

    public InputHintBindings();

    internal static System.Void CollectHintItems(Game.UI.InputHintBindings+InputHint hint, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType device, Game.Input.UIBaseInputAction+Transform transform, System.Boolean ignoreMask);
    private static System.Void CollectHints(System.Collections.Generic.Dictionary<System.ValueTuple<System.String, System.Int32>, Game.UI.InputHintBindings+InputHint> hints, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType device, System.Boolean ignoreMask);
    public System.Void Dispose();
    private Game.UI.InputHintBindings+InputHint GetInputHint(Game.UI.InputHintBindings+InputHintQuery query);
    private static Game.UI.InputHintBindings+InputHint[] GetTutorialHints(Game.UI.InputHintBindings+TutorialInputHintQuery query);
    private System.Void HandleInputHintPerformed(System.String action);
    private static System.Boolean MatchesControlScheme(Game.Input.ProxyBinding binding, Game.Input.InputManager+ControlScheme controlScheme);
    private static System.Boolean MatchesDirections(System.String[] bindings, System.String basePath, System.String[] dirs);
    private System.Void OnActionDisplayNamesChanged();
    private System.Void OnActionsChanged();
    private System.Void OnActiveDeviceChanged(UnityEngine.InputSystem.InputDevice newDevice, UnityEngine.InputSystem.InputDevice oldDevice, System.Boolean schemeChanged);
    private System.Void OnControlSchemeChanged(Game.Input.InputManager+ControlScheme controlScheme);
    private System.Void OnEnabledActionsChanged();
    private System.Void RebuildHints();
    private static System.Void SimplifyPaths(System.String[]& paths);
    public virtual System.Boolean Update();
}
```


## Fields

- `private readonly Colossal.UI.Binding.ValueBinding<Game.UI.InputHintBindings+InputHint[]> m_ActiveHintsBinding`  

```csharp
private readonly Colossal.UI.Binding.ValueBinding<Game.UI.InputHintBindings+InputHint[]> m_ActiveHintsBinding;
```

- `private readonly Colossal.UI.Binding.GetterMapBinding<Game.UI.InputHintBindings+InputHintQuery, Game.UI.InputHintBindings+InputHint> m_HintsMapBinding`  

```csharp
private readonly Colossal.UI.Binding.GetterMapBinding<Game.UI.InputHintBindings+InputHintQuery, Game.UI.InputHintBindings+InputHint> m_HintsMapBinding;
```

- `private readonly Colossal.UI.Binding.ValueBinding<System.Int32> m_GamepadTypeBinding`  

```csharp
private readonly Colossal.UI.Binding.ValueBinding<System.Int32> m_GamepadTypeBinding;
```

- `private readonly Colossal.UI.Binding.GetterMapBinding<Game.UI.InputHintBindings+TutorialInputHintQuery, Game.UI.InputHintBindings+InputHint[]> m_TutorialHints`  

```csharp
private readonly Colossal.UI.Binding.GetterMapBinding<Game.UI.InputHintBindings+TutorialInputHintQuery, Game.UI.InputHintBindings+InputHint[]> m_TutorialHints;
```

- `private System.Collections.Generic.Dictionary<System.ValueTuple<System.String, System.Int32>, Game.UI.InputHintBindings+InputHint> m_Hints`  

```csharp
private System.Collections.Generic.Dictionary<System.ValueTuple<System.String, System.Int32>, Game.UI.InputHintBindings+InputHint> m_Hints;
```

- `private System.Boolean m_HintsDirty`  

```csharp
private System.Boolean m_HintsDirty;
```

- `private System.Boolean m_TutorialHintsDirty`  

```csharp
private System.Boolean m_TutorialHintsDirty;
```

- `private System.Action<Game.Input.ProxyAction> onInputHintPerformed`  

```csharp
private System.Action<Game.Input.ProxyAction> onInputHintPerformed;
```

- `private static readonly System.String[] axisControls`  

```csharp
private static readonly System.String[] axisControls;
```

- `private static readonly System.String[] allDirs`  

```csharp
private static readonly System.String[] allDirs;
```

- `private static readonly System.String[] horizontal`  

```csharp
private static readonly System.String[] horizontal;
```

- `private static readonly System.String[] vertical`  

```csharp
private static readonly System.String[] vertical;
```

- `private static readonly System.String[] axes`  

```csharp
private static readonly System.String[] axes;
```

- `private static System.Collections.Generic.Dictionary<System.Collections.Generic.IReadOnlyList<Game.Input.ProxyModifier>, System.Collections.Generic.List<Game.Input.ProxyBinding>> modifiersGroups`  

```csharp
private static System.Collections.Generic.Dictionary<System.Collections.Generic.IReadOnlyList<Game.Input.ProxyModifier>, System.Collections.Generic.List<Game.Input.ProxyBinding>> modifiersGroups;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Constructors

- `public InputHintBindings()`  

```csharp
public InputHintBindings();
```


## Methods

- `internal static CollectHintItems(Game.UI.InputHintBindings+InputHint hint, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType device, Game.Input.UIBaseInputAction+Transform transform, System.Boolean ignoreMask = True) : System.Void`  

```csharp
internal static System.Void CollectHintItems(Game.UI.InputHintBindings+InputHint hint, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType device, Game.Input.UIBaseInputAction+Transform transform, System.Boolean ignoreMask);
```

- `private static CollectHints(System.Collections.Generic.Dictionary<System.ValueTuple<System.String, System.Int32>, Game.UI.InputHintBindings+InputHint> hints, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType device, System.Boolean ignoreMask = False) : System.Void`  

```csharp
private static System.Void CollectHints(System.Collections.Generic.Dictionary<System.ValueTuple<System.String, System.Int32>, Game.UI.InputHintBindings+InputHint> hints, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType device, System.Boolean ignoreMask);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `private GetInputHint(Game.UI.InputHintBindings+InputHintQuery query) : Game.UI.InputHintBindings+InputHint`  

```csharp
private Game.UI.InputHintBindings+InputHint GetInputHint(Game.UI.InputHintBindings+InputHintQuery query);
```

- `private static GetTutorialHints(Game.UI.InputHintBindings+TutorialInputHintQuery query) : Game.UI.InputHintBindings+InputHint[]`  

```csharp
private static Game.UI.InputHintBindings+InputHint[] GetTutorialHints(Game.UI.InputHintBindings+TutorialInputHintQuery query);
```

- `private HandleInputHintPerformed(System.String action) : System.Void`  

```csharp
private System.Void HandleInputHintPerformed(System.String action);
```

- `private static MatchesControlScheme(Game.Input.ProxyBinding binding, Game.Input.InputManager+ControlScheme controlScheme) : System.Boolean`  

```csharp
private static System.Boolean MatchesControlScheme(Game.Input.ProxyBinding binding, Game.Input.InputManager+ControlScheme controlScheme);
```

- `private static MatchesDirections(System.String[] bindings, System.String basePath, System.String[] dirs) : System.Boolean`  

```csharp
private static System.Boolean MatchesDirections(System.String[] bindings, System.String basePath, System.String[] dirs);
```

- `private OnActionDisplayNamesChanged() : System.Void`  

```csharp
private System.Void OnActionDisplayNamesChanged();
```

- `private OnActionsChanged() : System.Void`  

```csharp
private System.Void OnActionsChanged();
```

- `private OnActiveDeviceChanged(UnityEngine.InputSystem.InputDevice newDevice, UnityEngine.InputSystem.InputDevice oldDevice, System.Boolean schemeChanged) : System.Void`  

```csharp
private System.Void OnActiveDeviceChanged(UnityEngine.InputSystem.InputDevice newDevice, UnityEngine.InputSystem.InputDevice oldDevice, System.Boolean schemeChanged);
```

- `private OnControlSchemeChanged(Game.Input.InputManager+ControlScheme controlScheme) : System.Void`  

```csharp
private System.Void OnControlSchemeChanged(Game.Input.InputManager+ControlScheme controlScheme);
```

- `private OnEnabledActionsChanged() : System.Void`  

```csharp
private System.Void OnEnabledActionsChanged();
```

- `private RebuildHints() : System.Void`  

```csharp
private System.Void RebuildHints();
```

- `private static SimplifyPaths(System.String[]& paths) : System.Void`  

```csharp
private static System.Void SimplifyPaths(System.String[]& paths);
```

- `public virtual Update() : System.Boolean`  

```csharp
public virtual System.Boolean Update();
```


## Events

- `onInputHintPerformed` : `System.Action<Game.Input.ProxyAction>`  

```csharp
public event System.Action<Game.Input.ProxyAction> onInputHintPerformed;
```


## Nested types

- `Game.UI.InputHintBindings+InputHint`  
- `Game.UI.InputHintBindings+InputHintItem`  
- `Game.UI.InputHintBindings+TutorialInputHintQuery`  
- `Game.UI.InputHintBindings+InputHintQuery`  
- `Game.UI.InputHintBindings+<>c`  
- `Game.UI.InputHintBindings+<>c__DisplayClass29_0`  

