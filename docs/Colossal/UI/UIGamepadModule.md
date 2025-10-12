# Colossal.UI.UIGamepadModule

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `Colossal.UI.UIInputModule`  
**Implements:** `System.IDisposable`  

## Fields

- `private System.Int32 m_GamepadButtonsCount`  
- `private System.Int32 m_GamepadAxesCount`  
- `private System.Collections.Generic.Dictionary<System.UInt32, Colossal.UI.UIInputModule+GamepadMap> m_Gamepads`  
- `private static UnityEngine.InputSystem.InputAction s_ButtonAction`  
- `private static UnityEngine.InputSystem.InputAction s_DPadAction`  
- `private static UnityEngine.InputSystem.InputAction s_StickMoveAction`  
- `private static System.UInt32 s_DeviceIdCache`  
- `private static const System.Int32 kDefaultButtonsCount`  
- `private static const System.Int32 kDefaultAxesCount`  

## Constructors

- `public UIGamepadModule(Colossal.UI.UIInputSystem system)`  

## Methods

- `private AddGamepad(System.UInt32 id, System.String name) : System.Void`  
- `public virtual Disable() : System.Void`  
- `public virtual Dispose() : System.Void`  
- `public virtual Enable() : System.Void`  
- `private OnButtonAction(UnityEngine.InputSystem.InputAction+CallbackContext context) : System.Void`  
- `private OnDeviceChange(UnityEngine.InputSystem.InputDevice device, UnityEngine.InputSystem.InputDeviceChange deviceChange) : System.Void`  
- `private OnDpadAction(UnityEngine.InputSystem.InputAction+CallbackContext context) : System.Void`  
- `private OnStickMoveAction(UnityEngine.InputSystem.InputAction+CallbackContext context) : System.Void`  
- `private RemoveGamepad(System.UInt32 id) : System.Void`  
- `private SetAxis(UnityEngine.InputSystem.Controls.StickControl control, Colossal.UI.UIInputModule+GamepadMap currentGamepad) : System.Void`  
- `private SetButton(UnityEngine.InputSystem.Controls.ButtonControl control, Colossal.UI.UIInputModule+GamepadMap currentGamepad) : System.Void`  

## Nested types

- `Colossal.UI.UIGamepadModule+GamepadMapping`  

