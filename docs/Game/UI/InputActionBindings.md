# Game.UI.InputActionBindings

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `Colossal.UI.Binding.CompositeBinding`  
**Implements:** `Colossal.UI.Binding.IUpdateBinding`, `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IBindingRegistry`, `Colossal.UI.Binding.IBindingGroup`, `System.IDisposable`  

## Fields

- `private Colossal.UI.Binding.RawEventBinding m_ActionPerformedBinding`  
- `private Colossal.UI.Binding.RawEventBinding m_ActionReleasedBinding`  
- `private Colossal.UI.Binding.EventBinding m_ActionRefreshedBinding`  
- `private readonly System.Collections.Generic.List<Game.UI.InputActionBindings+ActionState> m_UIActionStates`  
- `private readonly System.Collections.Generic.Dictionary<System.ValueTuple<Game.Input.ProxyAction, Game.Input.UIBaseInputAction+ProcessAs>, Game.UI.InputActionBindings+IEventTrigger> m_Triggers`  
- `private readonly System.Collections.Generic.Dictionary<System.String, System.Int32> m_ActionOrder`  
- `private System.Boolean m_ActionsDirty`  
- `private System.Boolean m_ConflictsDirty`  
- `private System.Boolean m_UpdateInProgress`  
- `private static const System.Int32 kDisabledPriority`  
- `private static const System.String kGroup`  

## Constructors

- `public InputActionBindings()`  

## Methods

- `public Dispose() : System.Void`  
- `private OnActionsChanged() : System.Void`  
- `private OnControlSchemeChanged(Game.Input.InputManager+ControlScheme scheme) : System.Void`  
- `private RefreshActions() : System.Void`  
- `private ResolveConflicts() : System.Void`  
- `private SetActionPriority(System.String action, System.Int32 priority) : System.Void`  
- `private SetConflictsDirty() : System.Void`  
- `public virtual Update() : System.Boolean`  

## Nested types

- `Game.UI.InputActionBindings+ActionState`  
- `Game.UI.InputActionBindings+IEventTrigger`  
- `Game.UI.InputActionBindings+EventTrigger<TRawValue, TValue>`  
- `Game.UI.InputActionBindings+DefaultEventTrigger`  
- `Game.UI.InputActionBindings+ButtonEventTrigger`  
- `Game.UI.InputActionBindings+AxisEventTrigger`  
- `Game.UI.InputActionBindings+Vector2EventTrigger`  
- `Game.UI.InputActionBindings+AxisToButtonEventTrigger`  
- `Game.UI.InputActionBindings+Vector2ToButtonEventTrigger`  
- `Game.UI.InputActionBindings+ButtonToAxisEventTrigger`  
- `Game.UI.InputActionBindings+Vector2ToAxisEventTrigger`  
- `Game.UI.InputActionBindings+ButtonToVector2EventTrigger`  
- `Game.UI.InputActionBindings+AxisToVector2EventTrigger`  
- `Game.UI.InputActionBindings+<>c`  

