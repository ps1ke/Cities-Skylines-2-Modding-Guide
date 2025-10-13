# Game.Input.ControlPath

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `DebuggerDisplay`  

## Code

```csharp
public sealed struct ControlPath : Colossal.UI.Binding.IJsonWritable
{
    public System.String name;
    public Game.Input.InputManager+DeviceType device;
    public System.String displayName;
    private static System.Collections.Generic.Dictionary<System.String, System.Boolean> m_IsLatinLayout;

    public static Game.Input.ControlPath Get(System.String path);
    private static System.Boolean IsLatinLater(System.String displayName);
    public static System.Boolean IsLatinLikeLayout(UnityEngine.InputSystem.Keyboard keyboard);
    private static System.Boolean IsLatinOrPunctuation(System.String displayName);
    public static System.Boolean NeedLocalName(UnityEngine.InputSystem.Keyboard keyboard, UnityEngine.InputSystem.Controls.KeyControl control);
    public static System.String ToHumanReadablePath(System.String path, UnityEngine.InputSystem.InputControlPath+HumanReadableStringOptions options);
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public System.String name`  

```csharp
public System.String name;
```

- `public Game.Input.InputManager+DeviceType device`  

```csharp
public Game.Input.InputManager+DeviceType device;
```

- `public System.String displayName`  

```csharp
public System.String displayName;
```

- `private static System.Collections.Generic.Dictionary<System.String, System.Boolean> m_IsLatinLayout`  

```csharp
private static System.Collections.Generic.Dictionary<System.String, System.Boolean> m_IsLatinLayout;
```


## Methods

- `public static Get(System.String path) : Game.Input.ControlPath`  

```csharp
public static Game.Input.ControlPath Get(System.String path);
```

- `private static IsLatinLater(System.String displayName) : System.Boolean`  

```csharp
private static System.Boolean IsLatinLater(System.String displayName);
```

- `public static IsLatinLikeLayout(UnityEngine.InputSystem.Keyboard keyboard) : System.Boolean`  

```csharp
public static System.Boolean IsLatinLikeLayout(UnityEngine.InputSystem.Keyboard keyboard);
```

- `private static IsLatinOrPunctuation(System.String displayName) : System.Boolean`  

```csharp
private static System.Boolean IsLatinOrPunctuation(System.String displayName);
```

- `public static NeedLocalName(UnityEngine.InputSystem.Keyboard keyboard, UnityEngine.InputSystem.Controls.KeyControl control) : System.Boolean`  

```csharp
public static System.Boolean NeedLocalName(UnityEngine.InputSystem.Keyboard keyboard, UnityEngine.InputSystem.Controls.KeyControl control);
```

- `public static ToHumanReadablePath(System.String path, UnityEngine.InputSystem.InputControlPath+HumanReadableStringOptions options = OmitDevice) : System.String`  

```csharp
public static System.String ToHumanReadablePath(System.String path, UnityEngine.InputSystem.InputControlPath+HumanReadableStringOptions options);
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


## Nested types

- `Game.Input.ControlPath+<>c`  
- `Game.Input.ControlPath+<>c__DisplayClass5_0`  

