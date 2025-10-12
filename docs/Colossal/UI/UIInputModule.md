# Colossal.UI.UIInputModule

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Fields

- `private Colossal.UI.UIInputSystem m_System`  
- `protected static Colossal.Logging.ILog log`  

## Constructors

- `private UIInputModule()`  
- `public UIInputModule(Colossal.UI.UIInputSystem system)`  

## Methods

- `public virtual Disable() : System.Void`  
- `public virtual DispatchCustomInput() : System.Void`  
- `public virtual Dispose() : System.Void`  
- `public virtual Enable() : System.Void`  
- `protected EnqueueIMECompositionEvent(UnityEngine.InputSystem.LowLevel.IMECompositionString str) : System.Void`  
- `protected EnqueueInputEvent(cohtml.InputSystem.GenericInputEvent evt) : System.Void`  
- `protected RegisterNative(Colossal.UI.UIInputModule+GamepadMap gamepad) : System.Void`  
- `protected UnregisterNative(System.UInt32 id) : System.Void`  
- `protected UpdateGamepadStateNative(Colossal.UI.UIInputModule+GamepadMap gamepad) : System.Void`  

## Nested types

- `Colossal.UI.UIInputModule+GamepadMap`  

