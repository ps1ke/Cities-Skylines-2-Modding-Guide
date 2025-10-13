# Game.Input.UIInputCombinedAction+State

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.Input.IProxyAction`, `Game.Input.UIBaseInputAction+IState`  

## Code

```csharp
public class State : Game.Input.IProxyAction, Game.Input.UIBaseInputAction+IState
{
    private readonly Game.Input.UIInputAction+State[] m_States;

    public System.Collections.Generic.IReadOnlyList<Game.Input.ProxyAction> actions { get; }
    public System.Boolean enabled { get; set; }
    private System.Boolean Game.Input.IProxyAction.enabled { private get; private set; }

    public State(Game.Input.UIInputAction+State[] states);

    public System.Void Dispose();
    public System.Single GetMagnitude();
    public System.Boolean IsInProgress();
    public System.Boolean IsPressed();
    public T ReadValue<T>();
    public System.Boolean WasPressedThisFrame();
    public System.Boolean WasReleasedThisFrame();
}
```


## Fields

- `private readonly Game.Input.UIInputAction+State[] m_States`  

```csharp
private readonly Game.Input.UIInputAction+State[] m_States;
```


## Properties

- `public System.Collections.Generic.IReadOnlyList<Game.Input.ProxyAction> actions { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<Game.Input.ProxyAction> actions { get; }
```

- `public System.Boolean enabled { get; set }`  

```csharp
public System.Boolean enabled { get; set; }
```

- `private System.Boolean Game.Input.IProxyAction.enabled { private get; private set }`  

```csharp
private System.Boolean Game.Input.IProxyAction.enabled { private get; private set; }
```


## Constructors

- `public State(Game.Input.UIInputAction+State[] states)`  

```csharp
public State(Game.Input.UIInputAction+State[] states);
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public GetMagnitude() : System.Single`  

```csharp
public System.Single GetMagnitude();
```

- `public IsInProgress() : System.Boolean`  

```csharp
public System.Boolean IsInProgress();
```

- `public IsPressed() : System.Boolean`  

```csharp
public System.Boolean IsPressed();
```

- `public ReadValue<T>() : T`  

```csharp
public T ReadValue<T>();
```

- `public WasPressedThisFrame() : System.Boolean`  

```csharp
public System.Boolean WasPressedThisFrame();
```

- `public WasReleasedThisFrame() : System.Boolean`  

```csharp
public System.Boolean WasReleasedThisFrame();
```


## Events

- `onInteraction` : `System.Action<Game.Input.ProxyAction, UnityEngine.InputSystem.InputActionPhase>`  

```csharp
public event System.Action<Game.Input.ProxyAction, UnityEngine.InputSystem.InputActionPhase> onInteraction;
```


## Nested types

- `Game.Input.UIInputCombinedAction+State+<>c`  

