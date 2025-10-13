# Colossal.UI.UIInputSystem

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class UIInputSystem : System.IDisposable
{
    private Colossal.UI.UIKeyboardModule m_KeyboardModule;
    private Colossal.UI.UIMouseModule m_MouseModule;
    private Colossal.UI.UIGamepadModule m_GamepadModule;
    private System.Collections.Generic.List<Colossal.UI.UIInputModule> m_InputModules;
    private System.Collections.Generic.Queue<cohtml.InputSystem.GenericInputEvent> m_InputEvents;
    private System.String m_ActiveIMEComposition;
    private Colossal.UI.UISystem m_UISystem;
    private System.Boolean m_MouseEventPassed;
    private static Colossal.Logging.ILog log;
    private static const cohtml.InputSystem.GenericInputEvent+InputEventType AllInputEventTypes;

    public System.Boolean emulateBackspaceOnTextEvent { get; set; }
    public System.Boolean enableGamepadModule { set; }

    public UIInputSystem(Colossal.UI.UISystem uiSystem, System.Boolean enableGamepad);

    public System.Void Disable();
    public System.Void DispatchInputEvents(System.Boolean passMouseEvent);
    private System.Void DispatchInputEvents(Colossal.UI.UIView uiView, System.Boolean passMouseEvent, System.Boolean forceReceiveInput, cohtml.InputSystem.GenericInputEvent+InputEventType allInputEvents);
    public System.Void Dispose();
    public System.Void Enable();
    public System.Void EnqueueIMECompositionEvent(UnityEngine.InputSystem.LowLevel.IMECompositionString ime);
    public System.Void EnqueueInputEvent(cohtml.InputSystem.GenericInputEvent evt);
    public System.Void RegisterGamepad(System.UInt32 id, System.String gamepad, System.UInt32 axesCount, System.UInt32 buttonsCount);
    public System.Void RegisterInputModule(Colossal.UI.UIInputModule module);
    private static System.Void SetMousePosition(Colossal.UI.UIView uiView, UnityEngine.Vector2 mousePosition, cohtml.InputSystem.MouseEventDataCached mouseData);
    public System.Void UnregisterGamepad(System.UInt32 id);
    public System.Void UnregisterInputModule(Colossal.UI.UIInputModule module);
    public System.Void UpdateGamepadState(System.UInt32 id, System.Single[] axes, System.Single[] buttons);
}
```


## Fields

- `private Colossal.UI.UIKeyboardModule m_KeyboardModule`  

```csharp
private Colossal.UI.UIKeyboardModule m_KeyboardModule;
```

- `private Colossal.UI.UIMouseModule m_MouseModule`  

```csharp
private Colossal.UI.UIMouseModule m_MouseModule;
```

- `private Colossal.UI.UIGamepadModule m_GamepadModule`  

```csharp
private Colossal.UI.UIGamepadModule m_GamepadModule;
```

- `private System.Collections.Generic.List<Colossal.UI.UIInputModule> m_InputModules`  

```csharp
private System.Collections.Generic.List<Colossal.UI.UIInputModule> m_InputModules;
```

- `private System.Collections.Generic.Queue<cohtml.InputSystem.GenericInputEvent> m_InputEvents`  

```csharp
private System.Collections.Generic.Queue<cohtml.InputSystem.GenericInputEvent> m_InputEvents;
```

- `private System.String m_ActiveIMEComposition`  

```csharp
private System.String m_ActiveIMEComposition;
```

- `private Colossal.UI.UISystem m_UISystem`  

```csharp
private Colossal.UI.UISystem m_UISystem;
```

- `private System.Boolean m_MouseEventPassed`  

```csharp
private System.Boolean m_MouseEventPassed;
```

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```

- `private static const cohtml.InputSystem.GenericInputEvent+InputEventType AllInputEventTypes`  

```csharp
private static const cohtml.InputSystem.GenericInputEvent+InputEventType AllInputEventTypes;
```


## Properties

- `public System.Boolean emulateBackspaceOnTextEvent { get; set }`  

```csharp
public System.Boolean emulateBackspaceOnTextEvent { get; set; }
```

- `public System.Boolean enableGamepadModule { set }`  

```csharp
public System.Boolean enableGamepadModule { set; }
```


## Constructors

- `public UIInputSystem(Colossal.UI.UISystem uiSystem, System.Boolean enableGamepad = True)`  

```csharp
public UIInputSystem(Colossal.UI.UISystem uiSystem, System.Boolean enableGamepad);
```


## Methods

- `public Disable() : System.Void`  

```csharp
public System.Void Disable();
```

- `public DispatchInputEvents(System.Boolean passMouseEvent = True) : System.Void`  

```csharp
public System.Void DispatchInputEvents(System.Boolean passMouseEvent);
```

- `private DispatchInputEvents(Colossal.UI.UIView uiView, System.Boolean passMouseEvent, System.Boolean forceReceiveInput = False, cohtml.InputSystem.GenericInputEvent+InputEventType allInputEvents = Mouse, Touch, Key, Gesture) : System.Void`  

```csharp
private System.Void DispatchInputEvents(Colossal.UI.UIView uiView, System.Boolean passMouseEvent, System.Boolean forceReceiveInput, cohtml.InputSystem.GenericInputEvent+InputEventType allInputEvents);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public Enable() : System.Void`  

```csharp
public System.Void Enable();
```

- `public EnqueueIMECompositionEvent(UnityEngine.InputSystem.LowLevel.IMECompositionString ime) : System.Void`  

```csharp
public System.Void EnqueueIMECompositionEvent(UnityEngine.InputSystem.LowLevel.IMECompositionString ime);
```

- `public EnqueueInputEvent(cohtml.InputSystem.GenericInputEvent evt) : System.Void`  

```csharp
public System.Void EnqueueInputEvent(cohtml.InputSystem.GenericInputEvent evt);
```

- `public RegisterGamepad(System.UInt32 id, System.String gamepad, System.UInt32 axesCount, System.UInt32 buttonsCount) : System.Void`  

```csharp
public System.Void RegisterGamepad(System.UInt32 id, System.String gamepad, System.UInt32 axesCount, System.UInt32 buttonsCount);
```

- `public RegisterInputModule(Colossal.UI.UIInputModule module) : System.Void`  

```csharp
public System.Void RegisterInputModule(Colossal.UI.UIInputModule module);
```

- `private static SetMousePosition(Colossal.UI.UIView uiView, UnityEngine.Vector2 mousePosition, cohtml.InputSystem.MouseEventDataCached mouseData) : System.Void`  

```csharp
private static System.Void SetMousePosition(Colossal.UI.UIView uiView, UnityEngine.Vector2 mousePosition, cohtml.InputSystem.MouseEventDataCached mouseData);
```

- `public UnregisterGamepad(System.UInt32 id) : System.Void`  

```csharp
public System.Void UnregisterGamepad(System.UInt32 id);
```

- `public UnregisterInputModule(Colossal.UI.UIInputModule module) : System.Void`  

```csharp
public System.Void UnregisterInputModule(Colossal.UI.UIInputModule module);
```

- `public UpdateGamepadState(System.UInt32 id, System.Single[] axes, System.Single[] buttons) : System.Void`  

```csharp
public System.Void UpdateGamepadState(System.UInt32 id, System.Single[] axes, System.Single[] buttons);
```


