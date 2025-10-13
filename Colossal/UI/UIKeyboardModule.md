# Colossal.UI.UIKeyboardModule

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `Colossal.UI.UIInputModule`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class UIKeyboardModule : Colossal.UI.UIInputModule, System.IDisposable
{
    private readonly System.Collections.Generic.Dictionary<System.Int32, cohtml.InputSystem.KeyEventDataCached> m_PressedKeys;
    private System.Collections.Generic.List<UnityEngine.InputSystem.Keyboard> m_Keyboards;
    private System.Boolean <emulateBackspaceOnTextEvent>k__BackingField;
    private static UnityEngine.InputSystem.InputAction s_KeyboardAction;
    private static cohtml.InputSystem.DelayTimer s_KeyRepeatDelayTimer;
    private static cohtml.Net.EventModifiersState s_ModifiersState;
    private static const System.Single kKeyRepeatDelay;
    private static const System.Single kKeyRepeatRate;

    public System.Boolean emulateBackspaceOnTextEvent { get; set; }

    public UIKeyboardModule(Colossal.UI.UIInputSystem system);

    private System.Void AddKeyboard(UnityEngine.InputSystem.Keyboard keyboard);
    public virtual System.Void Disable();
    public virtual System.Void Dispose();
    public virtual System.Void Enable();
    public System.Void GenerateKeyEvents();
    public cohtml.Net.EventModifiersState GetKeyboardModifiers();
    private cohtml.Net.KeyEventData+EventLocation GetKeyLocation(cohtml.InputSystem.KeyEventDataCached evtData);
    private static System.Boolean IsModifierKey(System.Collections.Generic.Dictionary<System.Int32, cohtml.InputSystem.KeyEventDataCached> pressed);
    private System.Boolean IsNumPadKey(System.Int32 key);
    private System.Boolean IsSystemKey();
    private System.Void OnDeviceChange(UnityEngine.InputSystem.InputDevice device, UnityEngine.InputSystem.InputDeviceChange deviceChange);
    private System.Void OnIMECompositionChange(UnityEngine.InputSystem.LowLevel.IMECompositionString str);
    private System.Void OnKeyboardAction(UnityEngine.InputSystem.InputAction+CallbackContext context);
    private System.Void OnSendCharKey(System.Char character);
    private cohtml.InputSystem.KeyEventDataCached ProcessKeyEvent(UnityEngine.InputSystem.InputControl inputControl);
    private System.Void RemoveKeyboard(UnityEngine.InputSystem.Keyboard keyboard);
    private System.Void SetKeyCode(cohtml.InputSystem.KeyEventDataCached& eventData, System.Int32 keyCode);
    private System.Void SubscribeTextInput();
    private System.Void TextEventToKeyAction(System.Char character);
    private System.Void UnsubscribeTextInput();
    private cohtml.Net.EventModifiersState UpdateKeyboardModifiers(System.Boolean isControlDown, System.Boolean isAltDown, System.Boolean isShiftDown, System.Boolean isCapsLockDown, System.Boolean isMetaDown);
}
```


## Fields

- `private readonly System.Collections.Generic.Dictionary<System.Int32, cohtml.InputSystem.KeyEventDataCached> m_PressedKeys`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.Int32, cohtml.InputSystem.KeyEventDataCached> m_PressedKeys;
```

- `private System.Collections.Generic.List<UnityEngine.InputSystem.Keyboard> m_Keyboards`  

```csharp
private System.Collections.Generic.List<UnityEngine.InputSystem.Keyboard> m_Keyboards;
```

- `private System.Boolean <emulateBackspaceOnTextEvent>k__BackingField`  

```csharp
private System.Boolean <emulateBackspaceOnTextEvent>k__BackingField;
```

- `private static UnityEngine.InputSystem.InputAction s_KeyboardAction`  

```csharp
private static UnityEngine.InputSystem.InputAction s_KeyboardAction;
```

- `private static cohtml.InputSystem.DelayTimer s_KeyRepeatDelayTimer`  

```csharp
private static cohtml.InputSystem.DelayTimer s_KeyRepeatDelayTimer;
```

- `private static cohtml.Net.EventModifiersState s_ModifiersState`  

```csharp
private static cohtml.Net.EventModifiersState s_ModifiersState;
```

- `private static const System.Single kKeyRepeatDelay`  

```csharp
private static const System.Single kKeyRepeatDelay;
```

- `private static const System.Single kKeyRepeatRate`  

```csharp
private static const System.Single kKeyRepeatRate;
```


## Properties

- `public System.Boolean emulateBackspaceOnTextEvent { get; set }`  

```csharp
public System.Boolean emulateBackspaceOnTextEvent { get; set; }
```


## Constructors

- `public UIKeyboardModule(Colossal.UI.UIInputSystem system)`  

```csharp
public UIKeyboardModule(Colossal.UI.UIInputSystem system);
```


## Methods

- `private AddKeyboard(UnityEngine.InputSystem.Keyboard keyboard) : System.Void`  

```csharp
private System.Void AddKeyboard(UnityEngine.InputSystem.Keyboard keyboard);
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

- `public GenerateKeyEvents() : System.Void`  

```csharp
public System.Void GenerateKeyEvents();
```

- `public GetKeyboardModifiers() : cohtml.Net.EventModifiersState`  

```csharp
public cohtml.Net.EventModifiersState GetKeyboardModifiers();
```

- `private GetKeyLocation(cohtml.InputSystem.KeyEventDataCached evtData) : cohtml.Net.KeyEventData+EventLocation`  

```csharp
private cohtml.Net.KeyEventData+EventLocation GetKeyLocation(cohtml.InputSystem.KeyEventDataCached evtData);
```

- `private static IsModifierKey(System.Collections.Generic.Dictionary<System.Int32, cohtml.InputSystem.KeyEventDataCached> pressed) : System.Boolean`  

```csharp
private static System.Boolean IsModifierKey(System.Collections.Generic.Dictionary<System.Int32, cohtml.InputSystem.KeyEventDataCached> pressed);
```

- `private IsNumPadKey(System.Int32 key) : System.Boolean`  

```csharp
private System.Boolean IsNumPadKey(System.Int32 key);
```

- `private IsSystemKey() : System.Boolean`  

```csharp
private System.Boolean IsSystemKey();
```

- `private OnDeviceChange(UnityEngine.InputSystem.InputDevice device, UnityEngine.InputSystem.InputDeviceChange deviceChange) : System.Void`  

```csharp
private System.Void OnDeviceChange(UnityEngine.InputSystem.InputDevice device, UnityEngine.InputSystem.InputDeviceChange deviceChange);
```

- `private OnIMECompositionChange(UnityEngine.InputSystem.LowLevel.IMECompositionString str) : System.Void`  

```csharp
private System.Void OnIMECompositionChange(UnityEngine.InputSystem.LowLevel.IMECompositionString str);
```

- `private OnKeyboardAction(UnityEngine.InputSystem.InputAction+CallbackContext context) : System.Void`  

```csharp
private System.Void OnKeyboardAction(UnityEngine.InputSystem.InputAction+CallbackContext context);
```

- `private OnSendCharKey(System.Char character) : System.Void`  

```csharp
private System.Void OnSendCharKey(System.Char character);
```

- `private ProcessKeyEvent(UnityEngine.InputSystem.InputControl inputControl) : cohtml.InputSystem.KeyEventDataCached`  

```csharp
private cohtml.InputSystem.KeyEventDataCached ProcessKeyEvent(UnityEngine.InputSystem.InputControl inputControl);
```

- `private RemoveKeyboard(UnityEngine.InputSystem.Keyboard keyboard) : System.Void`  

```csharp
private System.Void RemoveKeyboard(UnityEngine.InputSystem.Keyboard keyboard);
```

- `private SetKeyCode(cohtml.InputSystem.KeyEventDataCached& eventData, System.Int32 keyCode) : System.Void`  

```csharp
private System.Void SetKeyCode(cohtml.InputSystem.KeyEventDataCached& eventData, System.Int32 keyCode);
```

- `private SubscribeTextInput() : System.Void`  

```csharp
private System.Void SubscribeTextInput();
```

- `private TextEventToKeyAction(System.Char character) : System.Void`  

```csharp
private System.Void TextEventToKeyAction(System.Char character);
```

- `private UnsubscribeTextInput() : System.Void`  

```csharp
private System.Void UnsubscribeTextInput();
```

- `private UpdateKeyboardModifiers(System.Boolean isControlDown, System.Boolean isAltDown, System.Boolean isShiftDown, System.Boolean isCapsLockDown, System.Boolean isMetaDown) : cohtml.Net.EventModifiersState`  

```csharp
private cohtml.Net.EventModifiersState UpdateKeyboardModifiers(System.Boolean isControlDown, System.Boolean isAltDown, System.Boolean isShiftDown, System.Boolean isCapsLockDown, System.Boolean isMetaDown);
```


## Nested types

- `Colossal.UI.UIKeyboardModule+KeyCodeMapping`  
- `Colossal.UI.UIKeyboardModule+<>c__DisplayClass25_0`  
- `Colossal.UI.UIKeyboardModule+<>c__DisplayClass27_0`  

