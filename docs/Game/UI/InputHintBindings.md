# Game.UI.InputHintBindings

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `Colossal.UI.Binding.CompositeBinding`  
**Implements:** `Colossal.UI.Binding.IUpdateBinding`, `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IBindingRegistry`, `Colossal.UI.Binding.IBindingGroup`, `System.IDisposable`  

## Fields

- `private readonly Colossal.UI.Binding.ValueBinding<Game.UI.InputHintBindings+InputHint[]> m_ActiveHintsBinding`  
- `private readonly Colossal.UI.Binding.GetterMapBinding<Game.UI.InputHintBindings+InputHintQuery, Game.UI.InputHintBindings+InputHint> m_HintsMapBinding`  
- `private readonly Colossal.UI.Binding.ValueBinding<System.Int32> m_GamepadTypeBinding`  
- `private readonly Colossal.UI.Binding.GetterMapBinding<Game.UI.InputHintBindings+TutorialInputHintQuery, Game.UI.InputHintBindings+InputHint[]> m_TutorialHints`  
- `private System.Collections.Generic.Dictionary<System.ValueTuple<System.String, System.Int32>, Game.UI.InputHintBindings+InputHint> m_Hints`  
- `private System.Boolean m_HintsDirty`  
- `private System.Boolean m_TutorialHintsDirty`  
- `private System.Action<Game.Input.ProxyAction> onInputHintPerformed`  
- `private static readonly System.String[] axisControls`  
- `private static readonly System.String[] allDirs`  
- `private static readonly System.String[] horizontal`  
- `private static readonly System.String[] vertical`  
- `private static readonly System.String[] axes`  
- `private static System.Collections.Generic.Dictionary<System.Collections.Generic.IReadOnlyList<Game.Input.ProxyModifier>, System.Collections.Generic.List<Game.Input.ProxyBinding>> modifiersGroups`  
- `private static const System.String kGroup`  

## Constructors

- `public InputHintBindings()`  

## Methods

- `internal static CollectHintItems(Game.UI.InputHintBindings+InputHint hint, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType device, Game.Input.UIBaseInputAction+Transform transform, System.Boolean ignoreMask = True) : System.Void`  
- `private static CollectHints(System.Collections.Generic.Dictionary<System.ValueTuple<System.String, System.Int32>, Game.UI.InputHintBindings+InputHint> hints, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType device, System.Boolean ignoreMask = False) : System.Void`  
- `public Dispose() : System.Void`  
- `private GetInputHint(Game.UI.InputHintBindings+InputHintQuery query) : Game.UI.InputHintBindings+InputHint`  
- `private static GetTutorialHints(Game.UI.InputHintBindings+TutorialInputHintQuery query) : Game.UI.InputHintBindings+InputHint[]`  
- `private HandleInputHintPerformed(System.String action) : System.Void`  
- `private static MatchesControlScheme(Game.Input.ProxyBinding binding, Game.Input.InputManager+ControlScheme controlScheme) : System.Boolean`  
- `private static MatchesDirections(System.String[] bindings, System.String basePath, System.String[] dirs) : System.Boolean`  
- `private OnActionDisplayNamesChanged() : System.Void`  
- `private OnActionsChanged() : System.Void`  
- `private OnActiveDeviceChanged(UnityEngine.InputSystem.InputDevice newDevice, UnityEngine.InputSystem.InputDevice oldDevice, System.Boolean schemeChanged) : System.Void`  
- `private OnControlSchemeChanged(Game.Input.InputManager+ControlScheme controlScheme) : System.Void`  
- `private OnEnabledActionsChanged() : System.Void`  
- `private RebuildHints() : System.Void`  
- `private static SimplifyPaths(System.String[]& paths) : System.Void`  
- `public virtual Update() : System.Boolean`  

## Events

- `onInputHintPerformed` : `System.Action<Game.Input.ProxyAction>`  

## Nested types

- `Game.UI.InputHintBindings+InputHint`  
- `Game.UI.InputHintBindings+InputHintItem`  
- `Game.UI.InputHintBindings+TutorialInputHintQuery`  
- `Game.UI.InputHintBindings+InputHintQuery`  
- `Game.UI.InputHintBindings+<>c`  
- `Game.UI.InputHintBindings+<>c__DisplayClass29_0`  

