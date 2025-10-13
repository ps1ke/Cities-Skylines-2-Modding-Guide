# Game.Input.CameraMoveProcessor

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `Game.Input.PlatformProcessor<UnityEngine.Vector2>`  

## Code

```csharp
public class CameraMoveProcessor : Game.Input.PlatformProcessor<UnityEngine.Vector2>
{
    public System.Single m_ScaleX;
    public System.Single m_ScaleY;

    public CameraMoveProcessor();

    public virtual UnityEngine.Vector2 Process(UnityEngine.Vector2 value, UnityEngine.InputSystem.InputControl control);
}
```


## Fields

- `public System.Single m_ScaleX`  

```csharp
public System.Single m_ScaleX;
```

- `public System.Single m_ScaleY`  

```csharp
public System.Single m_ScaleY;
```


## Constructors

- `public CameraMoveProcessor()`  

```csharp
public CameraMoveProcessor();
```


## Methods

- `public virtual Process(UnityEngine.Vector2 value, UnityEngine.InputSystem.InputControl control) : UnityEngine.Vector2`  

```csharp
public override Vector2 Process(Vector2 value, InputControl control)
	{
		if (!base.needProcess)
		{
			return value;
		}
		Game.Settings.InputSettings input = SharedSettings.instance.input;
		value.x *= m_ScaleX;
		value.y *= m_ScaleY;
		Vector2 vector = value;
		value = vector * m_DeviceType switch
		{
			ProcessorDeviceType.Mouse => input.mouseMoveSensitivity, 
			ProcessorDeviceType.Keyboard => input.keyboardMoveSensitivity, 
			ProcessorDeviceType.Gamepad => input.gamepadMoveSensitivity, 
			_ => 1f, 
		};
		return value;
	}
```


