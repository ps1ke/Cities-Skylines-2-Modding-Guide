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
public static ControlPath Get(string path)
	{
		if (string.IsNullOrEmpty(path))
		{
			return new ControlPath
			{
				name = string.Empty,
				device = InputManager.DeviceType.None,
				displayName = string.Empty
			};
		}
		InputControlPath.ParsedPathComponent[] source = InputControlPath.Parse(path).ToArray();
		string text = string.Join("/", from p in source
			where string.IsNullOrEmpty(p.layout)
			select p.name);
		string layout = source.FirstOrDefault((InputControlPath.ParsedPathComponent p) => !string.IsNullOrEmpty(p.layout)).layout;
		return new ControlPath
		{
			name = text,
			device = layout.ToDeviceType(),
			displayName = ((text.Length == 1 && char.IsLetter(text[0])) ? text.ToUpper() : text)
		};
	}
```

- `private static IsLatinLater(System.String displayName) : System.Boolean`  

```csharp
private static bool IsLatinLater(string displayName)
	{
		if (!string.IsNullOrEmpty(displayName) && char.IsLetterOrDigit(displayName[0]))
		{
			return displayName[0] <= 'ÿ';
		}
		return false;
	}
```

- `public static IsLatinLikeLayout(UnityEngine.InputSystem.Keyboard keyboard) : System.Boolean`  

```csharp
public static bool IsLatinLikeLayout(Keyboard keyboard)
	{
		if (!m_IsLatinLayout.TryGetValue(keyboard.keyboardLayout, out var value))
		{
			value = Enumerable.Range(15, 26).All((int k) => IsLatinOrPunctuation(keyboard[(Key)k].displayName));
			m_IsLatinLayout[keyboard.keyboardLayout] = value;
		}
		return value;
	}
```

- `private static IsLatinOrPunctuation(System.String displayName) : System.Boolean`  

```csharp
private static bool IsLatinOrPunctuation(string displayName)
	{
		if (!string.IsNullOrEmpty(displayName))
		{
			if (!IsLatinLater(displayName))
			{
				return char.IsPunctuation(displayName[0]);
			}
			return true;
		}
		return false;
	}
```

- `public static NeedLocalName(UnityEngine.InputSystem.Keyboard keyboard, UnityEngine.InputSystem.Controls.KeyControl control) : System.Boolean`  

```csharp
public static bool NeedLocalName(Keyboard keyboard, KeyControl control)
	{
		switch (control.keyCode)
		{
		case Key.Space:
		case Key.Enter:
		case Key.Tab:
		case Key.Digit1:
		case Key.Digit2:
		case Key.Digit3:
		case Key.Digit4:
		case Key.Digit5:
		case Key.Digit6:
		case Key.Digit7:
		case Key.Digit8:
		case Key.Digit9:
		case Key.Digit0:
		case Key.LeftShift:
		case Key.RightShift:
		case Key.LeftAlt:
		case Key.RightAlt:
		case Key.LeftCtrl:
		case Key.RightCtrl:
		case Key.LeftMeta:
		case Key.RightMeta:
		case Key.Escape:
		case Key.LeftArrow:
		case Key.RightArrow:
		case Key.UpArrow:
		case Key.DownArrow:
		case Key.Backspace:
		case Key.PageDown:
		case Key.PageUp:
		case Key.Home:
		case Key.End:
		case Key.Delete:
		case Key.Numpad0:
		case Key.Numpad1:
		case Key.Numpad2:
		case Key.Numpad3:
		case Key.Numpad4:
		case Key.Numpad5:
		case Key.Numpad6:
		case Key.Numpad7:
		case Key.Numpad8:
		case Key.Numpad9:
			return false;
		case Key.OEM1:
		case Key.OEM2:
		case Key.OEM3:
		case Key.OEM4:
		case Key.OEM5:
			return true;
		default:
			return IsLatinLikeLayout(keyboard);
		}
	}
```

- `public static ToHumanReadablePath(System.String path, UnityEngine.InputSystem.InputControlPath+HumanReadableStringOptions options = OmitDevice) : System.String`  

```csharp
public static string ToHumanReadablePath(string path, InputControlPath.HumanReadableStringOptions options = InputControlPath.HumanReadableStringOptions.OmitDevice)
	{
		return InputControlPath.ToHumanReadableString(path, options);
	}
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public void Write(IJsonWriter writer)
	{
		writer.TypeBegin(typeof(ControlPath).FullName);
		writer.PropertyName("name");
		writer.Write(name);
		writer.PropertyName("device");
		writer.Write(device.ToString());
		writer.PropertyName("displayName");
		writer.Write(displayName);
		writer.TypeEnd();
	}
```


## Nested types

- `Game.Input.ControlPath+<>c`  
- `Game.Input.ControlPath+<>c__DisplayClass5_0`  

