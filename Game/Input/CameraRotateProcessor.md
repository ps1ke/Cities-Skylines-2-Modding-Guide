# Game.Input.CameraRotateProcessor

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `Game.Input.PlatformProcessor<UnityEngine.Vector2>`  

## Code

```csharp
public class CameraRotateProcessor : Game.Input.PlatformProcessor<UnityEngine.Vector2>
{
    public System.Single m_ScaleX;
    public System.Single m_ScaleY;

    public CameraRotateProcessor();

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

- `public CameraRotateProcessor()`  

```csharp
public CameraRotateProcessor();
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
		ref float x = ref value.x;
		float num = x;
		x = num * m_DeviceType switch
		{
			ProcessorDeviceType.Mouse => input.mouseInvertX ? (0f - input.mouseRotateSensitivity) : input.mouseRotateSensitivity, 
			ProcessorDeviceType.Keyboard => input.keyboardRotateSensitivity, 
			ProcessorDeviceType.Gamepad => input.gamepadInvertX ? (0f - input.gamepadRotateSensitivity) : input.gamepadRotateSensitivity, 
			_ => 1f, 
		};
		x = ref value.y;
		float num2 = x;
		x = num2 * m_DeviceType switch
		{
			ProcessorDeviceType.Mouse => input.mouseInvertY ? (0f - input.mouseRotateSensitivity) : input.mouseRotateSensitivity, 
			ProcessorDeviceType.Keyboard => input.keyboardRotateSensitivity, 
			ProcessorDeviceType.Gamepad => (!input.gamepadInvertY) ? 1 : (-1), 
			_ => 1f, 
		};
		return value;
	}
```


