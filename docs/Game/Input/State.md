# Game.Input.UIInputCombinedAction+State

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.Input.IProxyAction`, `Game.Input.UIBaseInputAction+IState`  

## Fields

- `private readonly Game.Input.UIInputAction+State[] m_States`  

## Properties

- `public System.Collections.Generic.IReadOnlyList<Game.Input.ProxyAction> actions { get }`  
- `public System.Boolean enabled { get; set }`  
- `private System.Boolean Game.Input.IProxyAction.enabled { private get; private set }`  

## Constructors

- `public State(Game.Input.UIInputAction+State[] states)`  

## Methods

- `public Dispose() : System.Void`  
- `public GetMagnitude() : System.Single`  
- `public IsInProgress() : System.Boolean`  
- `public IsPressed() : System.Boolean`  
- `public ReadValue<T>() : T`  
- `public WasPressedThisFrame() : System.Boolean`  
- `public WasReleasedThisFrame() : System.Boolean`  

## Events

- `onInteraction` : `System.Action<Game.Input.ProxyAction, UnityEngine.InputSystem.InputActionPhase>`  

## Nested types

- `Game.Input.UIInputCombinedAction+State+<>c`  

