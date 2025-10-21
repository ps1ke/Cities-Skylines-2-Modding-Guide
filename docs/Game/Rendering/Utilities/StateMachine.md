# Game.Rendering.Utilities.StateMachine

**Assembly:** `Game`  
**Namespace:** `Game.Rendering.Utilities`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class StateMachine
{
    public System.Action onStarted;
    public System.Action onStopped;
    public System.Action<Game.Rendering.Utilities.State> onTransitioned;
    private System.String m_name;
    private Game.Rendering.Utilities.State _currentState;

    public System.String name { get; }
    public System.Boolean isStarted { get; }

    public StateMachine(System.String name);

    public System.String GetCurrentStateName();
    public System.Boolean IsIn<T>();
    public System.Void LateUpdate();
    public virtual System.Void Start(Game.Rendering.Utilities.State initialState);
    public virtual System.Void Stop();
    private System.Void TransitionTo(Game.Rendering.Utilities.State state);
    public System.Void Update();
}
```


## Fields

- `public System.Action onStarted`  

```csharp
public System.Action onStarted;
```

- `public System.Action onStopped`  

```csharp
public System.Action onStopped;
```

- `public System.Action<Game.Rendering.Utilities.State> onTransitioned`  

```csharp
public System.Action<Game.Rendering.Utilities.State> onTransitioned;
```

- `private System.String m_name`  

```csharp
private System.String m_name;
```

- `private Game.Rendering.Utilities.State _currentState`  

```csharp
private Game.Rendering.Utilities.State _currentState;
```


## Properties

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public System.Boolean isStarted { get }`  

```csharp
public System.Boolean isStarted { get; }
```


## Constructors

- `public StateMachine(System.String name = null)`  

```csharp
public StateMachine(System.String name);
```


## Methods

- `public GetCurrentStateName() : System.String`  

```csharp
public System.String GetCurrentStateName();
```

- `public IsIn<T>() : System.Boolean`  

```csharp
public System.Boolean IsIn<T>();
```

- `public LateUpdate() : System.Void`  

```csharp
public System.Void LateUpdate();
```

- `public virtual Start(Game.Rendering.Utilities.State initialState) : System.Void`  

```csharp
public virtual System.Void Start(Game.Rendering.Utilities.State initialState);
```

- `public virtual Stop() : System.Void`  

```csharp
public virtual System.Void Stop();
```

- `private TransitionTo(Game.Rendering.Utilities.State state) : System.Void`  

```csharp
private System.Void TransitionTo(Game.Rendering.Utilities.State state);
```

- `public Update() : System.Void`  

```csharp
public System.Void Update();
```


