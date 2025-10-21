# Game.UI.InputActionBindings

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `Colossal.UI.Binding.CompositeBinding`  
**Implements:** `Colossal.UI.Binding.IUpdateBinding`, `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IBindingRegistry`, `Colossal.UI.Binding.IBindingGroup`, `System.IDisposable`  

## Code

```csharp
public class InputActionBindings : Colossal.UI.Binding.CompositeBinding, Colossal.UI.Binding.IUpdateBinding, Colossal.UI.Binding.IBinding, Colossal.UI.Binding.IBindingRegistry, Colossal.UI.Binding.IBindingGroup, System.IDisposable
{
    private Colossal.UI.Binding.RawEventBinding m_ActionPerformedBinding;
    private Colossal.UI.Binding.RawEventBinding m_ActionReleasedBinding;
    private Colossal.UI.Binding.EventBinding m_ActionRefreshedBinding;
    private readonly System.Collections.Generic.List<Game.UI.InputActionBindings+ActionState> m_UIActionStates;
    private readonly System.Collections.Generic.Dictionary<System.ValueTuple<Game.Input.ProxyAction, Game.Input.UIBaseInputAction+ProcessAs>, Game.UI.InputActionBindings+IEventTrigger> m_Triggers;
    private readonly System.Collections.Generic.Dictionary<System.String, System.Int32> m_ActionOrder;
    private System.Boolean m_ActionsDirty;
    private System.Boolean m_ConflictsDirty;
    private System.Boolean m_UpdateInProgress;
    private static const System.Int32 kDisabledPriority;
    private static const System.String kGroup;

    public InputActionBindings();

    public System.Void Dispose();
    private System.Void OnActionsChanged();
    private System.Void OnControlSchemeChanged(Game.Input.InputManager+ControlScheme scheme);
    private System.Void RefreshActions();
    private System.Void ResolveConflicts();
    private System.Void SetActionPriority(System.String action, System.Int32 priority);
    private System.Void SetConflictsDirty();
    public virtual System.Boolean Update();
}
```


## Fields

- `private Colossal.UI.Binding.RawEventBinding m_ActionPerformedBinding`  

```csharp
private Colossal.UI.Binding.RawEventBinding m_ActionPerformedBinding;
```

- `private Colossal.UI.Binding.RawEventBinding m_ActionReleasedBinding`  

```csharp
private Colossal.UI.Binding.RawEventBinding m_ActionReleasedBinding;
```

- `private Colossal.UI.Binding.EventBinding m_ActionRefreshedBinding`  

```csharp
private Colossal.UI.Binding.EventBinding m_ActionRefreshedBinding;
```

- `private readonly System.Collections.Generic.List<Game.UI.InputActionBindings+ActionState> m_UIActionStates`  

```csharp
private readonly System.Collections.Generic.List<Game.UI.InputActionBindings+ActionState> m_UIActionStates;
```

- `private readonly System.Collections.Generic.Dictionary<System.ValueTuple<Game.Input.ProxyAction, Game.Input.UIBaseInputAction+ProcessAs>, Game.UI.InputActionBindings+IEventTrigger> m_Triggers`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.ValueTuple<Game.Input.ProxyAction, Game.Input.UIBaseInputAction+ProcessAs>, Game.UI.InputActionBindings+IEventTrigger> m_Triggers;
```

- `private readonly System.Collections.Generic.Dictionary<System.String, System.Int32> m_ActionOrder`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.String, System.Int32> m_ActionOrder;
```

- `private System.Boolean m_ActionsDirty`  

```csharp
private System.Boolean m_ActionsDirty;
```

- `private System.Boolean m_ConflictsDirty`  

```csharp
private System.Boolean m_ConflictsDirty;
```

- `private System.Boolean m_UpdateInProgress`  

```csharp
private System.Boolean m_UpdateInProgress;
```

- `private static const System.Int32 kDisabledPriority`  

```csharp
private static const System.Int32 kDisabledPriority;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Constructors

- `public InputActionBindings()`  

```csharp
public InputActionBindings();
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `private OnActionsChanged() : System.Void`  

```csharp
private System.Void OnActionsChanged();
```

- `private OnControlSchemeChanged(Game.Input.InputManager+ControlScheme scheme) : System.Void`  

```csharp
private System.Void OnControlSchemeChanged(Game.Input.InputManager+ControlScheme scheme);
```

- `private RefreshActions() : System.Void`  

```csharp
private System.Void RefreshActions();
```

- `private ResolveConflicts() : System.Void`  

```csharp
private System.Void ResolveConflicts();
```

- `private SetActionPriority(System.String action, System.Int32 priority) : System.Void`  

```csharp
private System.Void SetActionPriority(System.String action, System.Int32 priority);
```

- `private SetConflictsDirty() : System.Void`  

```csharp
private System.Void SetConflictsDirty();
```

- `public virtual Update() : System.Boolean`  

```csharp
public virtual System.Boolean Update();
```


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

