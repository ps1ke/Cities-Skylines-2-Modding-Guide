# Game.Rendering.Utilities.StateMachine

**Assembly:** `Game`  
**Namespace:** `Game.Rendering.Utilities`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `public System.Action onStarted`  
- `public System.Action onStopped`  
- `public System.Action<Game.Rendering.Utilities.State> onTransitioned`  
- `private System.String m_name`  
- `private Game.Rendering.Utilities.State _currentState`  

## Properties

- `public System.String name { get }`  
- `public System.Boolean isStarted { get }`  

## Constructors

- `public StateMachine(System.String name = null)`  

## Methods

- `public GetCurrentStateName() : System.String`  
- `public IsIn<T>() : System.Boolean`  
- `public LateUpdate() : System.Void`  
- `public virtual Start(Game.Rendering.Utilities.State initialState) : System.Void`  
- `public virtual Stop() : System.Void`  
- `private TransitionTo(Game.Rendering.Utilities.State state) : System.Void`  
- `public Update() : System.Void`  

