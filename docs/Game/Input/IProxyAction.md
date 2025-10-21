# Game.Input.IProxyAction

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IProxyAction
{
    public System.Boolean enabled { get; set; }

    public abstract System.Single GetMagnitude();
    public abstract System.Boolean IsInProgress();
    public abstract System.Boolean IsPressed();
    public abstract T ReadValue<T>();
    public abstract System.Boolean WasPressedThisFrame();
    public abstract System.Boolean WasReleasedThisFrame();
}
```


## Properties

- `public System.Boolean enabled { get; set }`  

```csharp
public System.Boolean enabled { get; set; }
```


## Methods

- `public abstract GetMagnitude() : System.Single`  

```csharp
public abstract System.Single GetMagnitude();
```

- `public abstract IsInProgress() : System.Boolean`  

```csharp
public abstract System.Boolean IsInProgress();
```

- `public abstract IsPressed() : System.Boolean`  

```csharp
public abstract System.Boolean IsPressed();
```

- `public abstract ReadValue<T>() : T`  

```csharp
public abstract T ReadValue<T>();
```

- `public abstract WasPressedThisFrame() : System.Boolean`  

```csharp
public abstract System.Boolean WasPressedThisFrame();
```

- `public abstract WasReleasedThisFrame() : System.Boolean`  

```csharp
public abstract System.Boolean WasReleasedThisFrame();
```


## Events

- `onInteraction` : `System.Action<Game.Input.ProxyAction, UnityEngine.InputSystem.InputActionPhase>`  

```csharp
public event System.Action<Game.Input.ProxyAction, UnityEngine.InputSystem.InputActionPhase> onInteraction;
```


