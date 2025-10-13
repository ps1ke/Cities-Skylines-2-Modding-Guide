# Colossal.UI.UIMouseModule

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `Colossal.UI.UIInputModule`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class UIMouseModule : Colossal.UI.UIInputModule, System.IDisposable
{
    private cohtml.InputSystem.GenericInputEvent m_MouseMoveData;
    private cohtml.InputSystem.GenericInputEvent m_MouseScrollData;
    private Colossal.UI.UIKeyboardModule m_Keyboard;
    private UnityEngine.Vector2 <lastMouseDownPosition>k__BackingField;
    private UnityEngine.Vector2 <lastMouseUpPosition>k__BackingField;
    private static UnityEngine.InputSystem.InputAction s_MouseAction;
    private static UnityEngine.InputSystem.InputAction s_MouseVectorAction;
    private static cohtml.Net.EventMouseModifiersState s_MouseModifiers;
    private static const System.String kDeltaString;
    private static const System.String kScrollString;
    private static const System.String kPressString;
    private static const System.Int16 kSkipCallsNumber;
    private static const System.Single kScrollMultiplier;

    public UnityEngine.Vector2 lastMouseDownPosition { get; private set; }
    public UnityEngine.Vector2 lastMouseUpPosition { get; private set; }
    public UnityEngine.Vector2 pointerScreenPosition { get; }

    public UIMouseModule(Colossal.UI.UIInputSystem system, Colossal.UI.UIKeyboardModule keyboard);

    public virtual System.Void Disable();
    public virtual System.Void Dispose();
    public virtual System.Void Enable();
    private cohtml.Net.EventMouseModifiersState GetMouseModifiers();
    private System.Void OnMouseAction(UnityEngine.InputSystem.InputAction+CallbackContext context);
    private System.Void OnMouseVectorAction(UnityEngine.InputSystem.InputAction+CallbackContext context);
    private System.Void OnPrimaryAction(UnityEngine.InputSystem.InputAction+CallbackContext context);
    private System.Void OnSecondaryAction(UnityEngine.InputSystem.InputAction+CallbackContext context);
    private System.Void ProcessScrollEvent();
    private System.Void SetLastPosition(cohtml.Net.MouseEventData+EventType eventType);
}
```


## Fields

- `private cohtml.InputSystem.GenericInputEvent m_MouseMoveData`  

```csharp
private cohtml.InputSystem.GenericInputEvent m_MouseMoveData;
```

- `private cohtml.InputSystem.GenericInputEvent m_MouseScrollData`  

```csharp
private cohtml.InputSystem.GenericInputEvent m_MouseScrollData;
```

- `private Colossal.UI.UIKeyboardModule m_Keyboard`  

```csharp
private Colossal.UI.UIKeyboardModule m_Keyboard;
```

- `private UnityEngine.Vector2 <lastMouseDownPosition>k__BackingField`  

```csharp
private UnityEngine.Vector2 <lastMouseDownPosition>k__BackingField;
```

- `private UnityEngine.Vector2 <lastMouseUpPosition>k__BackingField`  

```csharp
private UnityEngine.Vector2 <lastMouseUpPosition>k__BackingField;
```

- `private static UnityEngine.InputSystem.InputAction s_MouseAction`  

```csharp
private static UnityEngine.InputSystem.InputAction s_MouseAction;
```

- `private static UnityEngine.InputSystem.InputAction s_MouseVectorAction`  

```csharp
private static UnityEngine.InputSystem.InputAction s_MouseVectorAction;
```

- `private static cohtml.Net.EventMouseModifiersState s_MouseModifiers`  

```csharp
private static cohtml.Net.EventMouseModifiersState s_MouseModifiers;
```

- `private static const System.String kDeltaString`  

```csharp
private static const System.String kDeltaString;
```

- `private static const System.String kScrollString`  

```csharp
private static const System.String kScrollString;
```

- `private static const System.String kPressString`  

```csharp
private static const System.String kPressString;
```

- `private static const System.Int16 kSkipCallsNumber`  

```csharp
private static const System.Int16 kSkipCallsNumber;
```

- `private static const System.Single kScrollMultiplier`  

```csharp
private static const System.Single kScrollMultiplier;
```


## Properties

- `public UnityEngine.Vector2 lastMouseDownPosition { get; private set }`  

```csharp
public UnityEngine.Vector2 lastMouseDownPosition { get; private set; }
```

- `public UnityEngine.Vector2 lastMouseUpPosition { get; private set }`  

```csharp
public UnityEngine.Vector2 lastMouseUpPosition { get; private set; }
```

- `public UnityEngine.Vector2 pointerScreenPosition { get }`  

```csharp
public UnityEngine.Vector2 pointerScreenPosition { get; }
```


## Constructors

- `public UIMouseModule(Colossal.UI.UIInputSystem system, Colossal.UI.UIKeyboardModule keyboard)`  

```csharp
public UIMouseModule(Colossal.UI.UIInputSystem system, Colossal.UI.UIKeyboardModule keyboard);
```


## Methods

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

- `private GetMouseModifiers() : cohtml.Net.EventMouseModifiersState`  

```csharp
private cohtml.Net.EventMouseModifiersState GetMouseModifiers();
```

- `private OnMouseAction(UnityEngine.InputSystem.InputAction+CallbackContext context) : System.Void`  

```csharp
private System.Void OnMouseAction(UnityEngine.InputSystem.InputAction+CallbackContext context);
```

- `private OnMouseVectorAction(UnityEngine.InputSystem.InputAction+CallbackContext context) : System.Void`  

```csharp
private System.Void OnMouseVectorAction(UnityEngine.InputSystem.InputAction+CallbackContext context);
```

- `private OnPrimaryAction(UnityEngine.InputSystem.InputAction+CallbackContext context) : System.Void`  

```csharp
private System.Void OnPrimaryAction(UnityEngine.InputSystem.InputAction+CallbackContext context);
```

- `private OnSecondaryAction(UnityEngine.InputSystem.InputAction+CallbackContext context) : System.Void`  

```csharp
private System.Void OnSecondaryAction(UnityEngine.InputSystem.InputAction+CallbackContext context);
```

- `private ProcessScrollEvent() : System.Void`  

```csharp
private System.Void ProcessScrollEvent();
```

- `private SetLastPosition(cohtml.Net.MouseEventData+EventType eventType) : System.Void`  

```csharp
private System.Void SetLastPosition(cohtml.Net.MouseEventData+EventType eventType);
```


