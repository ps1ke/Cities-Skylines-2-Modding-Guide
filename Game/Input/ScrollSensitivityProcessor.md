# Game.Input.ScrollSensitivityProcessor

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `UnityEngine.InputSystem.InputProcessor<System.Single>`  

## Code

```csharp
public class ScrollSensitivityProcessor : UnityEngine.InputSystem.InputProcessor<System.Single>
{
    public ScrollSensitivityProcessor();

    public virtual System.Single Process(System.Single value, UnityEngine.InputSystem.InputControl control);
}
```


## Constructors

- `public ScrollSensitivityProcessor()`  

```csharp
public ScrollSensitivityProcessor();
```


## Methods

- `public virtual Process(System.Single value, UnityEngine.InputSystem.InputControl control) : System.Single`  

```csharp
public override float Process(float value, InputControl control)
	{
		return value * SharedSettings.instance.input.finalScrollSensitivity;
	}
```


