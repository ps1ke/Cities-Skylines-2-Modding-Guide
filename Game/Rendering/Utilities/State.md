# Game.Rendering.Utilities.State

**Assembly:** `Game`  
**Namespace:** `Game.Rendering.Utilities`  

**Type:** class abstract public  

**Base:** `System.Object`  

## Code

```csharp
public abstract class State
{
    private Game.Rendering.Utilities.StateMachine _machine;
    private System.String <Name>k__BackingField;

    public Game.Rendering.Utilities.StateMachine machine { get; set; }
    public System.String Name { get; set; }

    public State();

    public virtual System.Void LateUpdate();
    public virtual System.Void TransitionIn();
    public virtual System.Void TransitionOut();
    public virtual Game.Rendering.Utilities.State+Result Update();
}
```


## Fields

- `private Game.Rendering.Utilities.StateMachine _machine`  

```csharp
private Game.Rendering.Utilities.StateMachine _machine;
```

- `private System.String <Name>k__BackingField`  

```csharp
private System.String <Name>k__BackingField;
```


## Properties

- `public Game.Rendering.Utilities.StateMachine machine { get; set }`  

```csharp
public Game.Rendering.Utilities.StateMachine machine { get; set; }
```

- `public System.String Name { get; set }`  

```csharp
public System.String Name { get; set; }
```


## Constructors

- `public State()`  

```csharp
public State()
	{
	}
```


## Methods

- `public virtual LateUpdate() : System.Void`  

```csharp
public virtual void LateUpdate()
	{
	}
```

- `public virtual TransitionIn() : System.Void`  

```csharp
public virtual void TransitionIn()
	{
	}
```

- `public virtual TransitionOut() : System.Void`  

```csharp
public virtual void TransitionOut()
	{
		_machine = null;
	}
```

- `public virtual Update() : Game.Rendering.Utilities.State+Result`  

```csharp
public virtual Result Update()
	{
		return Result.Continue;
	}
```


## Nested types

- `Game.Rendering.Utilities.State+ResultType`  
- `Game.Rendering.Utilities.State+Result`  

