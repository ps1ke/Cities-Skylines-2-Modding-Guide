# Colossal.UI.UIMouseModule

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `Colossal.UI.UIInputModule`  
**Implements:** `System.IDisposable`  

## Fields

- `private cohtml.InputSystem.GenericInputEvent m_MouseMoveData`  
- `private cohtml.InputSystem.GenericInputEvent m_MouseScrollData`  
- `private Colossal.UI.UIKeyboardModule m_Keyboard`  
- `private UnityEngine.Vector2 <lastMouseDownPosition>k__BackingField`  
- `private UnityEngine.Vector2 <lastMouseUpPosition>k__BackingField`  
- `private static UnityEngine.InputSystem.InputAction s_MouseAction`  
- `private static UnityEngine.InputSystem.InputAction s_MouseVectorAction`  
- `private static cohtml.Net.EventMouseModifiersState s_MouseModifiers`  
- `private static const System.String kDeltaString`  
- `private static const System.String kScrollString`  
- `private static const System.String kPressString`  
- `private static const System.Int16 kSkipCallsNumber`  
- `private static const System.Single kScrollMultiplier`  

## Properties

- `public UnityEngine.Vector2 lastMouseDownPosition { get; private set }`  
- `public UnityEngine.Vector2 lastMouseUpPosition { get; private set }`  
- `public UnityEngine.Vector2 pointerScreenPosition { get }`  

## Constructors

- `public UIMouseModule(Colossal.UI.UIInputSystem system, Colossal.UI.UIKeyboardModule keyboard)`  

## Methods

- `public virtual Disable() : System.Void`  
- `public virtual Dispose() : System.Void`  
- `public virtual Enable() : System.Void`  
- `private GetMouseModifiers() : cohtml.Net.EventMouseModifiersState`  
- `private OnMouseAction(UnityEngine.InputSystem.InputAction+CallbackContext context) : System.Void`  
- `private OnMouseVectorAction(UnityEngine.InputSystem.InputAction+CallbackContext context) : System.Void`  
- `private OnPrimaryAction(UnityEngine.InputSystem.InputAction+CallbackContext context) : System.Void`  
- `private OnSecondaryAction(UnityEngine.InputSystem.InputAction+CallbackContext context) : System.Void`  
- `private ProcessScrollEvent() : System.Void`  
- `private SetLastPosition(cohtml.Net.MouseEventData+EventType eventType) : System.Void`  

