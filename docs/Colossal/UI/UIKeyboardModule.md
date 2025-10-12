# Colossal.UI.UIKeyboardModule

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `Colossal.UI.UIInputModule`  
**Implements:** `System.IDisposable`  

## Fields

- `private readonly System.Collections.Generic.Dictionary<System.Int32, cohtml.InputSystem.KeyEventDataCached> m_PressedKeys`  
- `private System.Collections.Generic.List<UnityEngine.InputSystem.Keyboard> m_Keyboards`  
- `private System.Boolean <emulateBackspaceOnTextEvent>k__BackingField`  
- `private static UnityEngine.InputSystem.InputAction s_KeyboardAction`  
- `private static cohtml.InputSystem.DelayTimer s_KeyRepeatDelayTimer`  
- `private static cohtml.Net.EventModifiersState s_ModifiersState`  
- `private static const System.Single kKeyRepeatDelay`  
- `private static const System.Single kKeyRepeatRate`  

## Properties

- `public System.Boolean emulateBackspaceOnTextEvent { get; set }`  

## Constructors

- `public UIKeyboardModule(Colossal.UI.UIInputSystem system)`  

## Methods

- `private AddKeyboard(UnityEngine.InputSystem.Keyboard keyboard) : System.Void`  
- `public virtual Disable() : System.Void`  
- `public virtual Dispose() : System.Void`  
- `public virtual Enable() : System.Void`  
- `public GenerateKeyEvents() : System.Void`  
- `public GetKeyboardModifiers() : cohtml.Net.EventModifiersState`  
- `private GetKeyLocation(cohtml.InputSystem.KeyEventDataCached evtData) : cohtml.Net.KeyEventData+EventLocation`  
- `private static IsModifierKey(System.Collections.Generic.Dictionary<System.Int32, cohtml.InputSystem.KeyEventDataCached> pressed) : System.Boolean`  
- `private IsNumPadKey(System.Int32 key) : System.Boolean`  
- `private IsSystemKey() : System.Boolean`  
- `private OnDeviceChange(UnityEngine.InputSystem.InputDevice device, UnityEngine.InputSystem.InputDeviceChange deviceChange) : System.Void`  
- `private OnIMECompositionChange(UnityEngine.InputSystem.LowLevel.IMECompositionString str) : System.Void`  
- `private OnKeyboardAction(UnityEngine.InputSystem.InputAction+CallbackContext context) : System.Void`  
- `private OnSendCharKey(System.Char character) : System.Void`  
- `private ProcessKeyEvent(UnityEngine.InputSystem.InputControl inputControl) : cohtml.InputSystem.KeyEventDataCached`  
- `private RemoveKeyboard(UnityEngine.InputSystem.Keyboard keyboard) : System.Void`  
- `private SetKeyCode(cohtml.InputSystem.KeyEventDataCached& eventData, System.Int32 keyCode) : System.Void`  
- `private SubscribeTextInput() : System.Void`  
- `private TextEventToKeyAction(System.Char character) : System.Void`  
- `private UnsubscribeTextInput() : System.Void`  
- `private UpdateKeyboardModifiers(System.Boolean isControlDown, System.Boolean isAltDown, System.Boolean isShiftDown, System.Boolean isCapsLockDown, System.Boolean isMetaDown) : cohtml.Net.EventModifiersState`  

## Nested types

- `Colossal.UI.UIKeyboardModule+KeyCodeMapping`  
- `Colossal.UI.UIKeyboardModule+<>c__DisplayClass25_0`  
- `Colossal.UI.UIKeyboardModule+<>c__DisplayClass27_0`  

