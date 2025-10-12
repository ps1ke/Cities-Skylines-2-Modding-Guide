# Game.Input.IProxyAction

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** interface abstract public  


## Properties

- `public System.Boolean enabled { get; set }`  

## Methods

- `public abstract GetMagnitude() : System.Single`  
- `public abstract IsInProgress() : System.Boolean`  
- `public abstract IsPressed() : System.Boolean`  
- `public abstract ReadValue<T>() : T`  
- `public abstract WasPressedThisFrame() : System.Boolean`  
- `public abstract WasReleasedThisFrame() : System.Boolean`  

## Events

- `onInteraction` : `System.Action<Game.Input.ProxyAction, UnityEngine.InputSystem.InputActionPhase>`  

