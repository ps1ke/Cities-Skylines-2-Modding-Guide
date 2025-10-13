# Game.Input.UIButtonInteraction

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `UnityEngine.InputSystem.IInputInteraction`  

## Code

```csharp
public class UIButtonInteraction : UnityEngine.InputSystem.IInputInteraction
{
    public System.Single repeatDelay;
    public System.Single repeatRate;
    public System.Single pressPoint;

    private System.Single pressPointOrDefault { private get; }

    public UIButtonInteraction();

    private static System.Void Init();
    public System.Void Process(UnityEngine.InputSystem.InputInteractionContext& context);
    public System.Void Reset();
}
```


## Fields

- `public System.Single repeatDelay`  

```csharp
public System.Single repeatDelay;
```

- `public System.Single repeatRate`  

```csharp
public System.Single repeatRate;
```

- `public System.Single pressPoint`  

```csharp
public System.Single pressPoint;
```


## Properties

- `private System.Single pressPointOrDefault { private get }`  

```csharp
private System.Single pressPointOrDefault { private get; }
```


## Constructors

- `public UIButtonInteraction()`  

```csharp
static UIButtonInteraction()
	{
		InputSystem.RegisterInteraction<UIButtonInteraction>();
	}
```


## Methods

- `private static Init() : System.Void`  

```csharp
private static void Init()
	{
	}
```

- `public Process(UnityEngine.InputSystem.InputInteractionContext& context) : System.Void`  

```csharp
public void Process(ref InputInteractionContext context)
	{
		switch (context.phase)
		{
		case InputActionPhase.Waiting:
			if (context.ControlIsActuated(pressPointOrDefault))
			{
				context.Started();
				context.PerformedAndStayStarted();
				context.SetTimeout(repeatDelay);
			}
			break;
		case InputActionPhase.Started:
			if (context.timerHasExpired)
			{
				context.PerformedAndStayStarted();
				context.SetTimeout(repeatRate);
			}
			else if (!context.ControlIsActuated(pressPointOrDefault))
			{
				context.Canceled();
			}
			break;
		}
	}
```

- `public Reset() : System.Void`  

```csharp
public void Reset()
	{
	}
```


