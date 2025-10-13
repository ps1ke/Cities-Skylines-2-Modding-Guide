# Game.PSI.VirtualKeyboard

**Assembly:** `Game`  
**Namespace:** `Game.PSI`  

**Type:** class public  

**Base:** `Colossal.UI.TextInputHandler`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class VirtualKeyboard : Colossal.UI.TextInputHandler, System.IDisposable
{
    public VirtualKeyboard();

    private System.Void <.ctor>b__0_0(Colossal.PSI.Common.IVirtualKeyboardSupport psi, System.String text);
    private System.String GetVkDescription();
    private System.String GetVkTitle();
    private Colossal.PSI.Common.InputType GetVkType();
    protected virtual System.Void OnBlurCallback();
    protected virtual System.Void OnFocusCallback(System.String str);
    private Colossal.PSI.Common.InputType TextToInputType(System.String text);
}
```


## Constructors

- `public VirtualKeyboard()`  

```csharp
public VirtualKeyboard()
	{
		PlatformManager.instance.onInputDismissed += delegate(IVirtualKeyboardSupport psi, string text)
		{
			if (!psi.passThroughVKeyboard)
			{
				RefreshText(text);
			}
		};
	}
```


## Methods

- `private <.ctor>b__0_0(Colossal.PSI.Common.IVirtualKeyboardSupport psi, System.String text) : System.Void`  

```csharp
private System.Void <.ctor>b__0_0(Colossal.PSI.Common.IVirtualKeyboardSupport psi, System.String text);
```

- `private GetVkDescription() : System.String`  

```csharp
private string GetVkDescription()
	{
		string attribute = base.proxy.GetAttribute("vk-description");
		if (!string.IsNullOrEmpty(attribute))
		{
			return attribute;
		}
		return string.Empty;
	}
```

- `private GetVkTitle() : System.String`  

```csharp
private string GetVkTitle()
	{
		string attribute = base.proxy.GetAttribute("vk-title");
		if (!string.IsNullOrEmpty(attribute))
		{
			return attribute;
		}
		return "Input";
	}
```

- `private GetVkType() : Colossal.PSI.Common.InputType`  

```csharp
private InputType GetVkType()
	{
		string attribute = base.proxy.GetAttribute("vk-type");
		return TextToInputType(attribute);
	}
```

- `protected virtual OnBlurCallback() : System.Void`  

```csharp
protected override void OnBlurCallback()
	{
		GameManager.UIInputSystem.emulateBackspaceOnTextEvent = false;
		PlatformManager.instance.DismissVirtualKeyboard();
	}
```

- `protected virtual OnFocusCallback(System.String str) : System.Void`  

```csharp
protected override void OnFocusCallback(string str)
	{
		if (InputManager.instance.activeControlScheme == InputManager.ControlScheme.Gamepad)
		{
			bool flag = PlatformManager.instance.ShowVirtualKeyboard(GetVkType(), GetVkTitle(), GetVkDescription(), 100, str);
			GameManager.UIInputSystem.emulateBackspaceOnTextEvent = flag && PlatformManager.instance.passThroughVKeyboard;
		}
	}
```

- `private TextToInputType(System.String text) : Colossal.PSI.Common.InputType`  

```csharp
private InputType TextToInputType(string text)
	{
		return text switch
		{
			"text" => InputType.Text, 
			"password" => InputType.Password, 
			"email" => InputType.Email, 
			_ => InputType.Other, 
		};
	}
```


