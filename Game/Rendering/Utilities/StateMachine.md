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
public StateMachine(string name = null)
	{
		m_name = name;
	}
```


## Methods

- `public GetCurrentStateName() : System.String`  

```csharp
public string GetCurrentStateName()
	{
		if (_currentState != null)
		{
			if (!string.IsNullOrEmpty(_currentState.Name))
			{
				return _currentState.Name;
			}
			return _currentState.ToString();
		}
		return "none";
	}
```

- `public IsIn<T>() : System.Boolean`  

```csharp
public System.Boolean IsIn<T>();
```

- `public LateUpdate() : System.Void`  

```csharp
public void LateUpdate()
	{
		if (isStarted)
		{
			_currentState.LateUpdate();
		}
	}
```

- `public virtual Start(Game.Rendering.Utilities.State initialState) : System.Void`  

```csharp
public virtual void Start(State initialState)
	{
		if (!isStarted && initialState != null)
		{
			TransitionTo(initialState);
			onStarted.Fire();
			return;
		}
		throw new Exception("already started");
	}
```

- `public virtual Stop() : System.Void`  

```csharp
public virtual void Stop()
	{
		if (isStarted)
		{
			if (_currentState != null)
			{
				_currentState.TransitionOut();
				_currentState = null;
			}
			onStopped.Fire();
		}
	}
```

- `private TransitionTo(Game.Rendering.Utilities.State state) : System.Void`  

```csharp
private void TransitionTo(State state)
	{
		_currentState?.TransitionOut();
		_currentState = state;
		_currentState.machine = this;
		_currentState.TransitionIn();
		onTransitioned.Fire(_currentState);
		Update();
	}
```

- `public Update() : System.Void`  

```csharp
public void Update()
	{
		if (isStarted)
		{
			State.Result result = _currentState.Update();
			switch (result.type)
			{
			case State.ResultType.Stop:
				Stop();
				break;
			case State.ResultType.Transition:
				TransitionTo(result.next);
				break;
			case State.ResultType.Continue:
				break;
			}
		}
	}
```


