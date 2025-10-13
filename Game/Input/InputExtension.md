# Game.Input.InputExtension

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class InputExtension
{
    public static System.String GetInteractions(UnityEngine.InputSystem.InputBinding binding, Game.Input.InputManager+PathType pathType);
    public static System.String GetPath(UnityEngine.InputSystem.InputBinding binding, Game.Input.InputManager+PathType pathType);
    public static System.String GetProcessors(UnityEngine.InputSystem.InputBinding binding, Game.Input.InputManager+PathType pathType);
    public static Game.Input.InputManager+DeviceType ToDeviceType(System.Nullable<UnityEngine.InputSystem.InputBinding> mask);
    public static Game.Input.InputManager+DeviceType ToDeviceType(System.String group);
    public static Game.Input.InputManager+DeviceType ToDeviceType(Game.Input.InputManager+ControlScheme scheme);
    public static System.Nullable<UnityEngine.InputSystem.InputBinding> ToInputBinding(Game.Input.InputManager+DeviceType type);
    public static Game.Input.UIBaseInputAction+Transform ToTransform(Game.Input.ActionComponent component);
}
```


## Methods

- `public static GetInteractions(UnityEngine.InputSystem.InputBinding binding, Game.Input.InputManager+PathType pathType) : System.String`  

```csharp
public static string GetInteractions(this InputBinding binding, InputManager.PathType pathType)
	{
		return pathType switch
		{
			InputManager.PathType.Effective => binding.effectiveInteractions, 
			InputManager.PathType.Original => binding.interactions, 
			InputManager.PathType.Overridden => binding.overrideInteractions, 
			_ => binding.effectivePath, 
		};
	}
```

- `public static GetPath(UnityEngine.InputSystem.InputBinding binding, Game.Input.InputManager+PathType pathType) : System.String`  

```csharp
public static string GetPath(this InputBinding binding, InputManager.PathType pathType)
	{
		return pathType switch
		{
			InputManager.PathType.Effective => binding.effectivePath, 
			InputManager.PathType.Original => binding.path, 
			InputManager.PathType.Overridden => binding.overridePath, 
			_ => binding.effectivePath, 
		};
	}
```

- `public static GetProcessors(UnityEngine.InputSystem.InputBinding binding, Game.Input.InputManager+PathType pathType) : System.String`  

```csharp
public static string GetProcessors(this InputBinding binding, InputManager.PathType pathType)
	{
		return pathType switch
		{
			InputManager.PathType.Effective => binding.effectiveProcessors, 
			InputManager.PathType.Original => binding.processors, 
			InputManager.PathType.Overridden => binding.overrideProcessors, 
			_ => binding.effectivePath, 
		};
	}
```

- `public static ToDeviceType(System.Nullable<UnityEngine.InputSystem.InputBinding> mask) : Game.Input.InputManager+DeviceType`  

```csharp
public static InputManager.DeviceType ToDeviceType(this InputManager.ControlScheme scheme)
	{
		return scheme switch
		{
			InputManager.ControlScheme.KeyboardAndMouse => InputManager.DeviceType.Keyboard | InputManager.DeviceType.Mouse, 
			InputManager.ControlScheme.Gamepad => InputManager.DeviceType.Gamepad, 
			_ => InputManager.DeviceType.None, 
		};
	}
```

- `public static ToDeviceType(System.String group) : Game.Input.InputManager+DeviceType`  

```csharp
public static InputManager.DeviceType ToDeviceType(this InputManager.ControlScheme scheme)
	{
		return scheme switch
		{
			InputManager.ControlScheme.KeyboardAndMouse => InputManager.DeviceType.Keyboard | InputManager.DeviceType.Mouse, 
			InputManager.ControlScheme.Gamepad => InputManager.DeviceType.Gamepad, 
			_ => InputManager.DeviceType.None, 
		};
	}
```

- `public static ToDeviceType(Game.Input.InputManager+ControlScheme scheme) : Game.Input.InputManager+DeviceType`  

```csharp
public static InputManager.DeviceType ToDeviceType(this InputManager.ControlScheme scheme)
	{
		return scheme switch
		{
			InputManager.ControlScheme.KeyboardAndMouse => InputManager.DeviceType.Keyboard | InputManager.DeviceType.Mouse, 
			InputManager.ControlScheme.Gamepad => InputManager.DeviceType.Gamepad, 
			_ => InputManager.DeviceType.None, 
		};
	}
```

- `public static ToInputBinding(Game.Input.InputManager+DeviceType type) : System.Nullable<UnityEngine.InputSystem.InputBinding>`  

```csharp
public static System.Nullable<UnityEngine.InputSystem.InputBinding> ToInputBinding(Game.Input.InputManager+DeviceType type);
```

- `public static ToTransform(Game.Input.ActionComponent component) : Game.Input.UIBaseInputAction+Transform`  

```csharp
public static UIBaseInputAction.Transform ToTransform(this ActionComponent component)
	{
		return component switch
		{
			ActionComponent.Press => UIBaseInputAction.Transform.Press, 
			ActionComponent.Negative => UIBaseInputAction.Transform.Negative, 
			ActionComponent.Positive => UIBaseInputAction.Transform.Positive, 
			ActionComponent.Down => UIBaseInputAction.Transform.Down, 
			ActionComponent.Up => UIBaseInputAction.Transform.Up, 
			ActionComponent.Left => UIBaseInputAction.Transform.Left, 
			ActionComponent.Right => UIBaseInputAction.Transform.Right, 
			_ => UIBaseInputAction.Transform.Press, 
		};
	}
```


