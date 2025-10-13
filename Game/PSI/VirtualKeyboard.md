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
public VirtualKeyboard();
```


## Methods

- `private <.ctor>b__0_0(Colossal.PSI.Common.IVirtualKeyboardSupport psi, System.String text) : System.Void`  

```csharp
private System.Void <.ctor>b__0_0(Colossal.PSI.Common.IVirtualKeyboardSupport psi, System.String text);
```

- `private GetVkDescription() : System.String`  

```csharp
private System.String GetVkDescription();
```

- `private GetVkTitle() : System.String`  

```csharp
private System.String GetVkTitle();
```

- `private GetVkType() : Colossal.PSI.Common.InputType`  

```csharp
private Colossal.PSI.Common.InputType GetVkType();
```

- `protected virtual OnBlurCallback() : System.Void`  

```csharp
protected virtual System.Void OnBlurCallback();
```

- `protected virtual OnFocusCallback(System.String str) : System.Void`  

```csharp
protected virtual System.Void OnFocusCallback(System.String str);
```

- `private TextToInputType(System.String text) : Colossal.PSI.Common.InputType`  

```csharp
private Colossal.PSI.Common.InputType TextToInputType(System.String text);
```


