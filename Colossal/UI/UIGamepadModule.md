# Colossal.UI.UIGamepadModule

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `Colossal.UI.UIInputModule`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class UIGamepadModule : Colossal.UI.UIInputModule, System.IDisposable
{
    private System.Int32 m_GamepadButtonsCount;
    private System.Int32 m_GamepadAxesCount;
    private System.Collections.Generic.Dictionary<System.UInt32, Colossal.UI.UIInputModule+GamepadMap> m_Gamepads;
    private static UnityEngine.InputSystem.InputAction s_ButtonAction;
    private static UnityEngine.InputSystem.InputAction s_DPadAction;
    private static UnityEngine.InputSystem.InputAction s_StickMoveAction;
    private static System.UInt32 s_DeviceIdCache;
    private static const System.Int32 kDefaultButtonsCount;
    private static const System.Int32 kDefaultAxesCount;

    public UIGamepadModule(Colossal.UI.UIInputSystem system);

    private System.Void AddGamepad(System.UInt32 id, System.String name);
    public virtual System.Void Disable();
    public virtual System.Void Dispose();
    public virtual System.Void Enable();
    private System.Void OnButtonAction(UnityEngine.InputSystem.InputAction+CallbackContext context);
    private System.Void OnDeviceChange(UnityEngine.InputSystem.InputDevice device, UnityEngine.InputSystem.InputDeviceChange deviceChange);
    private System.Void OnDpadAction(UnityEngine.InputSystem.InputAction+CallbackContext context);
    private System.Void OnStickMoveAction(UnityEngine.InputSystem.InputAction+CallbackContext context);
    private System.Void RemoveGamepad(System.UInt32 id);
    private System.Void SetAxis(UnityEngine.InputSystem.Controls.StickControl control, Colossal.UI.UIInputModule+GamepadMap currentGamepad);
    private System.Void SetButton(UnityEngine.InputSystem.Controls.ButtonControl control, Colossal.UI.UIInputModule+GamepadMap currentGamepad);
}
```


## Fields

- `private System.Int32 m_GamepadButtonsCount`  

```csharp
private System.Int32 m_GamepadButtonsCount;
```

- `private System.Int32 m_GamepadAxesCount`  

```csharp
private System.Int32 m_GamepadAxesCount;
```

- `private System.Collections.Generic.Dictionary<System.UInt32, Colossal.UI.UIInputModule+GamepadMap> m_Gamepads`  

```csharp
private System.Collections.Generic.Dictionary<System.UInt32, Colossal.UI.UIInputModule+GamepadMap> m_Gamepads;
```

- `private static UnityEngine.InputSystem.InputAction s_ButtonAction`  

```csharp
private static UnityEngine.InputSystem.InputAction s_ButtonAction;
```

- `private static UnityEngine.InputSystem.InputAction s_DPadAction`  

```csharp
private static UnityEngine.InputSystem.InputAction s_DPadAction;
```

- `private static UnityEngine.InputSystem.InputAction s_StickMoveAction`  

```csharp
private static UnityEngine.InputSystem.InputAction s_StickMoveAction;
```

- `private static System.UInt32 s_DeviceIdCache`  

```csharp
private static System.UInt32 s_DeviceIdCache;
```

- `private static const System.Int32 kDefaultButtonsCount`  

```csharp
private static const System.Int32 kDefaultButtonsCount;
```

- `private static const System.Int32 kDefaultAxesCount`  

```csharp
private static const System.Int32 kDefaultAxesCount;
```


## Constructors

- `public UIGamepadModule(Colossal.UI.UIInputSystem system)`  

```csharp
public UIGamepadModule(Colossal.UI.UIInputSystem system);
```


## Methods

- `private AddGamepad(System.UInt32 id, System.String name) : System.Void`  

```csharp
private System.Void AddGamepad(System.UInt32 id, System.String name);
```

- `public virtual Disable() : System.Void`  

```csharp
public virtual System.Void Disable();
```

- `public virtual Dispose() : System.Void`  

```csharp
public virtual System.Void Dispose();
```

- `public virtual Enable() : System.Void`  

```csharp
public virtual System.Void Enable();
```

- `private OnButtonAction(UnityEngine.InputSystem.InputAction+CallbackContext context) : System.Void`  

```csharp
private System.Void OnButtonAction(UnityEngine.InputSystem.InputAction+CallbackContext context);
```

- `private OnDeviceChange(UnityEngine.InputSystem.InputDevice device, UnityEngine.InputSystem.InputDeviceChange deviceChange) : System.Void`  

```csharp
private System.Void OnDeviceChange(UnityEngine.InputSystem.InputDevice device, UnityEngine.InputSystem.InputDeviceChange deviceChange);
```

- `private OnDpadAction(UnityEngine.InputSystem.InputAction+CallbackContext context) : System.Void`  

```csharp
private System.Void OnDpadAction(UnityEngine.InputSystem.InputAction+CallbackContext context);
```

- `private OnStickMoveAction(UnityEngine.InputSystem.InputAction+CallbackContext context) : System.Void`  

```csharp
private System.Void OnStickMoveAction(UnityEngine.InputSystem.InputAction+CallbackContext context);
```

- `private RemoveGamepad(System.UInt32 id) : System.Void`  

```csharp
private System.Void RemoveGamepad(System.UInt32 id);
```

- `private SetAxis(UnityEngine.InputSystem.Controls.StickControl control, Colossal.UI.UIInputModule+GamepadMap currentGamepad) : System.Void`  

```csharp
private System.Void SetAxis(UnityEngine.InputSystem.Controls.StickControl control, Colossal.UI.UIInputModule+GamepadMap currentGamepad);
```

- `private SetButton(UnityEngine.InputSystem.Controls.ButtonControl control, Colossal.UI.UIInputModule+GamepadMap currentGamepad) : System.Void`  

```csharp
private System.Void SetButton(UnityEngine.InputSystem.Controls.ButtonControl control, Colossal.UI.UIInputModule+GamepadMap currentGamepad);
```


## Nested types

- `Colossal.UI.UIGamepadModule+GamepadMapping`  

