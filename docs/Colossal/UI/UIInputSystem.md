# Colossal.UI.UIInputSystem

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Fields

- `private Colossal.UI.UIKeyboardModule m_KeyboardModule`  
- `private Colossal.UI.UIMouseModule m_MouseModule`  
- `private Colossal.UI.UIGamepadModule m_GamepadModule`  
- `private System.Collections.Generic.List<Colossal.UI.UIInputModule> m_InputModules`  
- `private System.Collections.Generic.Queue<cohtml.InputSystem.GenericInputEvent> m_InputEvents`  
- `private System.String m_ActiveIMEComposition`  
- `private Colossal.UI.UISystem m_UISystem`  
- `private System.Boolean m_MouseEventPassed`  
- `private static Colossal.Logging.ILog log`  
- `private static const cohtml.InputSystem.GenericInputEvent+InputEventType AllInputEventTypes`  

## Properties

- `public System.Boolean emulateBackspaceOnTextEvent { get; set }`  
- `public System.Boolean enableGamepadModule { set }`  

## Constructors

- `public UIInputSystem(Colossal.UI.UISystem uiSystem, System.Boolean enableGamepad = True)`  

## Methods

- `public Disable() : System.Void`  
- `public DispatchInputEvents(System.Boolean passMouseEvent = True) : System.Void`  
- `private DispatchInputEvents(Colossal.UI.UIView uiView, System.Boolean passMouseEvent, System.Boolean forceReceiveInput = False, cohtml.InputSystem.GenericInputEvent+InputEventType allInputEvents = Mouse, Touch, Key, Gesture) : System.Void`  
- `public Dispose() : System.Void`  
- `public Enable() : System.Void`  
- `public EnqueueIMECompositionEvent(UnityEngine.InputSystem.LowLevel.IMECompositionString ime) : System.Void`  
- `public EnqueueInputEvent(cohtml.InputSystem.GenericInputEvent evt) : System.Void`  
- `public RegisterGamepad(System.UInt32 id, System.String gamepad, System.UInt32 axesCount, System.UInt32 buttonsCount) : System.Void`  
- `public RegisterInputModule(Colossal.UI.UIInputModule module) : System.Void`  
- `private static SetMousePosition(Colossal.UI.UIView uiView, UnityEngine.Vector2 mousePosition, cohtml.InputSystem.MouseEventDataCached mouseData) : System.Void`  
- `public UnregisterGamepad(System.UInt32 id) : System.Void`  
- `public UnregisterInputModule(Colossal.UI.UIInputModule module) : System.Void`  
- `public UpdateGamepadState(System.UInt32 id, System.Single[] axes, System.Single[] buttons) : System.Void`  

