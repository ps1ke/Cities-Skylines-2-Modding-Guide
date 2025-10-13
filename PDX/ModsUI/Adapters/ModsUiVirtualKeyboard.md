# PDX.ModsUI.Adapters.ModsUiVirtualKeyboard

**Assembly:** `PDX.ModsUI`  
**Namespace:** `PDX.ModsUI.Adapters`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `PDX.ModsUI.Adapters.IModsUiVirtualKeyboard`  

## Code

```csharp
public class ModsUiVirtualKeyboard : PDX.ModsUI.Adapters.IModsUiVirtualKeyboard
{
    public ModsUiVirtualKeyboard();

    public System.Void ShowScreenKeyboard(System.String title, System.String description, System.String defaultText, System.UInt32 maxTextLength, System.Action<System.Boolean, System.String> submitResultCallback);
}
```


## Constructors

- `public ModsUiVirtualKeyboard()`  

```csharp
public ModsUiVirtualKeyboard();
```


## Methods

- `public ShowScreenKeyboard(System.String title, System.String description, System.String defaultText, System.UInt32 maxTextLength, System.Action<System.Boolean, System.String> submitResultCallback) : System.Void`  

```csharp
public System.Void ShowScreenKeyboard(System.String title, System.String description, System.String defaultText, System.UInt32 maxTextLength, System.Action<System.Boolean, System.String> submitResultCallback);
```


