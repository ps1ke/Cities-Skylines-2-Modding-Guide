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
public static System.String GetInteractions(UnityEngine.InputSystem.InputBinding binding, Game.Input.InputManager+PathType pathType);
```

- `public static GetPath(UnityEngine.InputSystem.InputBinding binding, Game.Input.InputManager+PathType pathType) : System.String`  

```csharp
public static System.String GetPath(UnityEngine.InputSystem.InputBinding binding, Game.Input.InputManager+PathType pathType);
```

- `public static GetProcessors(UnityEngine.InputSystem.InputBinding binding, Game.Input.InputManager+PathType pathType) : System.String`  

```csharp
public static System.String GetProcessors(UnityEngine.InputSystem.InputBinding binding, Game.Input.InputManager+PathType pathType);
```

- `public static ToDeviceType(System.Nullable<UnityEngine.InputSystem.InputBinding> mask) : Game.Input.InputManager+DeviceType`  

```csharp
public static Game.Input.InputManager+DeviceType ToDeviceType(System.Nullable<UnityEngine.InputSystem.InputBinding> mask);
```

- `public static ToDeviceType(System.String group) : Game.Input.InputManager+DeviceType`  

```csharp
public static Game.Input.InputManager+DeviceType ToDeviceType(System.String group);
```

- `public static ToDeviceType(Game.Input.InputManager+ControlScheme scheme) : Game.Input.InputManager+DeviceType`  

```csharp
public static Game.Input.InputManager+DeviceType ToDeviceType(Game.Input.InputManager+ControlScheme scheme);
```

- `public static ToInputBinding(Game.Input.InputManager+DeviceType type) : System.Nullable<UnityEngine.InputSystem.InputBinding>`  

```csharp
public static System.Nullable<UnityEngine.InputSystem.InputBinding> ToInputBinding(Game.Input.InputManager+DeviceType type);
```

- `public static ToTransform(Game.Input.ActionComponent component) : Game.Input.UIBaseInputAction+Transform`  

```csharp
public static Game.Input.UIBaseInputAction+Transform ToTransform(Game.Input.ActionComponent component);
```


