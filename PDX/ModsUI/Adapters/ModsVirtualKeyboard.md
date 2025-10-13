# PDX.ModsUI.Adapters.ModsVirtualKeyboard

**Assembly:** `PDX.ModsUI`  
**Namespace:** `PDX.ModsUI.Adapters`  

**Type:** class public  

**Base:** `cohtml.TextInputHandler`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class ModsVirtualKeyboard : cohtml.TextInputHandler, System.IDisposable
{
    public ModsVirtualKeyboard();

    private System.Void <FocusCallback>b__1_0(System.Boolean success, System.String outputText);
    public System.String BlurCallback();
    public System.Void FocusCallback(System.String input);
    protected System.Void RefreshText(System.String text);
    public System.Void ShowScreenKeyboard(System.String title, System.String description, System.String defaultText, System.UInt32 maxTextLength, System.Action<System.Boolean, System.String> submitResultCallback);
}
```


## Constructors

- `public ModsVirtualKeyboard()`  

```csharp
public ModsVirtualKeyboard();
```


## Methods

- `private <FocusCallback>b__1_0(System.Boolean success, System.String outputText) : System.Void`  

```csharp
private System.Void <FocusCallback>b__1_0(System.Boolean success, System.String outputText);
```

- `public BlurCallback() : System.String`  

```csharp
public System.String BlurCallback();
```

- `public FocusCallback(System.String input) : System.Void`  

```csharp
public System.Void FocusCallback(System.String input);
```

- `protected RefreshText(System.String text) : System.Void`  

```csharp
protected System.Void RefreshText(System.String text);
```

- `public ShowScreenKeyboard(System.String title, System.String description, System.String defaultText, System.UInt32 maxTextLength, System.Action<System.Boolean, System.String> submitResultCallback) : System.Void`  

```csharp
public System.Void ShowScreenKeyboard(System.String title, System.String description, System.String defaultText, System.UInt32 maxTextLength, System.Action<System.Boolean, System.String> submitResultCallback);
```


