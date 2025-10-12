# Game.SceneFlow.OverlayBindings

**Assembly:** `Game`  
**Namespace:** `Game.SceneFlow`  

**Type:** class public  

**Base:** `Colossal.UI.Binding.CompositeBinding`  
**Implements:** `Colossal.UI.Binding.IUpdateBinding`, `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IBindingRegistry`, `Colossal.UI.Binding.IBindingGroup`  

## Fields

- `private System.Action<Game.SceneFlow.OverlayScreen> onScreenActivated`  
- `private readonly Colossal.UI.Binding.ValueBinding<Game.SceneFlow.OverlayScreen> m_ActiveScreen`  
- `private readonly Colossal.UI.Binding.ValueBinding<System.Single[]> m_Progress`  
- `private readonly Colossal.UI.Binding.ValueBinding<System.String[]> m_HintMessages`  
- `private readonly Colossal.UI.Binding.ValueBinding<System.String[]> m_CorruptDataMessages`  
- `private readonly System.Collections.Generic.SortedSet<Game.SceneFlow.OverlayScreen> m_ActiveScreenList`  
- `private static const System.String kGroup`  

## Properties

- `public Game.SceneFlow.OverlayScreen currentlyActiveScreen { get }`  
- `public System.String[] hintMessages { get; set }`  
- `public System.String[] corruptDataMessages { get; set }`  

## Constructors

- `public OverlayBindings()`  

## Methods

- `public ActivateScreen(Game.SceneFlow.OverlayScreen screen) : System.Void`  
- `public ActivateScreenScoped(Game.SceneFlow.OverlayScreen screen) : Game.SceneFlow.OverlayBindings+ScopedScreen`  
- `public DeactivateAllScreens() : System.Void`  
- `public DeactivateScreen(Game.SceneFlow.OverlayScreen screen) : System.Void`  
- `public GetProgress(Game.SceneFlow.OverlayProgressType type) : System.Single`  
- `public SetProgress(Game.SceneFlow.OverlayProgressType type, System.Single progress) : System.Void`  
- `public SwapScreen(Game.SceneFlow.OverlayScreen screen1, Game.SceneFlow.OverlayScreen screen2) : System.Void`  
- `private UpdateScreen() : System.Void`  

## Events

- `onScreenActivated` : `System.Action<Game.SceneFlow.OverlayScreen>`  

## Nested types

- `Game.SceneFlow.OverlayBindings+ScopedScreen`  
- `Game.SceneFlow.OverlayBindings+<>c`  

