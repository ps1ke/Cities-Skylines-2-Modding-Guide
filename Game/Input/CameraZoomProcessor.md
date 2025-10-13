# Game.Input.CameraZoomProcessor

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `Game.Input.PlatformProcessor<System.Single>`  

## Code

```csharp
public class CameraZoomProcessor : Game.Input.PlatformProcessor<System.Single>
{
    public System.Single m_Scale;

    public CameraZoomProcessor();

    public virtual System.Single Process(System.Single value, UnityEngine.InputSystem.InputControl control);
}
```


## Fields

- `public System.Single m_Scale`  

```csharp
public System.Single m_Scale;
```


## Constructors

- `public CameraZoomProcessor()`  

```csharp
public CameraZoomProcessor();
```


## Methods

- `public virtual Process(System.Single value, UnityEngine.InputSystem.InputControl control) : System.Single`  

```csharp
public override float Process(float value, InputControl control)
	{
		if (!base.needProcess)
		{
			return value;
		}
		Game.Settings.InputSettings input = SharedSettings.instance.input;
		value *= m_Scale;
		float num = value;
		value = num * m_DeviceType switch
		{
			ProcessorDeviceType.Mouse => input.mouseZoomSensitivity, 
			ProcessorDeviceType.Keyboard => input.keyboardZoomSensitivity, 
			ProcessorDeviceType.Gamepad => input.gamepadZoomSensitivity, 
			_ => 1f, 
		};
		return value;
	}
```


