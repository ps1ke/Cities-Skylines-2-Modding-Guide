# Game.Input.ControlPath

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `DebuggerDisplay`  

## Fields

- `public System.String name`  
- `public Game.Input.InputManager+DeviceType device`  
- `public System.String displayName`  
- `private static System.Collections.Generic.Dictionary<System.String, System.Boolean> m_IsLatinLayout`  

## Methods

- `public static Get(System.String path) : Game.Input.ControlPath`  
- `private static IsLatinLater(System.String displayName) : System.Boolean`  
- `public static IsLatinLikeLayout(UnityEngine.InputSystem.Keyboard keyboard) : System.Boolean`  
- `private static IsLatinOrPunctuation(System.String displayName) : System.Boolean`  
- `public static NeedLocalName(UnityEngine.InputSystem.Keyboard keyboard, UnityEngine.InputSystem.Controls.KeyControl control) : System.Boolean`  
- `public static ToHumanReadablePath(System.String path, UnityEngine.InputSystem.InputControlPath+HumanReadableStringOptions options = OmitDevice) : System.String`  
- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

## Nested types

- `Game.Input.ControlPath+<>c`  
- `Game.Input.ControlPath+<>c__DisplayClass5_0`  

