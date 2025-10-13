# Colossal.UI.UIInputModule

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public abstract class UIInputModule : System.IDisposable
{
    private Colossal.UI.UIInputSystem m_System;
    protected static Colossal.Logging.ILog log;

    private UIInputModule();
    public UIInputModule(Colossal.UI.UIInputSystem system);

    public virtual System.Void Disable();
    public virtual System.Void DispatchCustomInput();
    public virtual System.Void Dispose();
    public virtual System.Void Enable();
    protected System.Void EnqueueIMECompositionEvent(UnityEngine.InputSystem.LowLevel.IMECompositionString str);
    protected System.Void EnqueueInputEvent(cohtml.InputSystem.GenericInputEvent evt);
    protected System.Void RegisterNative(Colossal.UI.UIInputModule+GamepadMap gamepad);
    protected System.Void UnregisterNative(System.UInt32 id);
    protected System.Void UpdateGamepadStateNative(Colossal.UI.UIInputModule+GamepadMap gamepad);
}
```


## Fields

- `private Colossal.UI.UIInputSystem m_System`  

```csharp
private Colossal.UI.UIInputSystem m_System;
```

- `protected static Colossal.Logging.ILog log`  

```csharp
protected static Colossal.Logging.ILog log;
```


## Constructors

- `private UIInputModule()`  

```csharp
private UIInputModule();
```

- `public UIInputModule(Colossal.UI.UIInputSystem system)`  

```csharp
public UIInputModule(Colossal.UI.UIInputSystem system);
```


## Methods

- `public virtual Disable() : System.Void`  

```csharp
public virtual System.Void Disable();
```

- `public virtual DispatchCustomInput() : System.Void`  

```csharp
public virtual System.Void DispatchCustomInput();
```

- `public virtual Dispose() : System.Void`  

```csharp
public virtual System.Void Dispose();
```

- `public virtual Enable() : System.Void`  

```csharp
public virtual System.Void Enable();
```

- `protected EnqueueIMECompositionEvent(UnityEngine.InputSystem.LowLevel.IMECompositionString str) : System.Void`  

```csharp
protected System.Void EnqueueIMECompositionEvent(UnityEngine.InputSystem.LowLevel.IMECompositionString str);
```

- `protected EnqueueInputEvent(cohtml.InputSystem.GenericInputEvent evt) : System.Void`  

```csharp
protected System.Void EnqueueInputEvent(cohtml.InputSystem.GenericInputEvent evt);
```

- `protected RegisterNative(Colossal.UI.UIInputModule+GamepadMap gamepad) : System.Void`  

```csharp
protected System.Void RegisterNative(Colossal.UI.UIInputModule+GamepadMap gamepad);
```

- `protected UnregisterNative(System.UInt32 id) : System.Void`  

```csharp
protected System.Void UnregisterNative(System.UInt32 id);
```

- `protected UpdateGamepadStateNative(Colossal.UI.UIInputModule+GamepadMap gamepad) : System.Void`  

```csharp
protected System.Void UpdateGamepadStateNative(Colossal.UI.UIInputModule+GamepadMap gamepad);
```


## Nested types

- `Colossal.UI.UIInputModule+GamepadMap`  

