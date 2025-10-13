# Colossal.PSI.Common.IVirtualKeyboardSupport

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** interface abstract public  

**Implements:** `Colossal.PSI.Common.IPlatformServiceIntegration`, `Colossal.PSI.Common.IDisposableAsync`  

## Code

```csharp
public abstract interface IVirtualKeyboardSupport : Colossal.PSI.Common.IPlatformServiceIntegration, Colossal.PSI.Common.IDisposableAsync
{
    public System.Boolean passThroughVKeyboard { get; }

    public abstract System.Void DismissVirtualKeyboard();
    public abstract System.Void SetActiveTextFieldRect(System.Int32 x, System.Int32 y, System.Int32 width, System.Int32 height);
    public abstract System.Boolean ShowVirtualKeyboard(Colossal.PSI.Common.InputType inputType, System.String title, System.String description, System.Int32 buffer, System.String previous);
}
```


## Properties

- `public System.Boolean passThroughVKeyboard { get }`  

```csharp
public System.Boolean passThroughVKeyboard { get; }
```


## Methods

- `public abstract DismissVirtualKeyboard() : System.Void`  

```csharp
public abstract System.Void DismissVirtualKeyboard();
```

- `public abstract SetActiveTextFieldRect(System.Int32 x, System.Int32 y, System.Int32 width, System.Int32 height) : System.Void`  

```csharp
public abstract System.Void SetActiveTextFieldRect(System.Int32 x, System.Int32 y, System.Int32 width, System.Int32 height);
```

- `public abstract ShowVirtualKeyboard(Colossal.PSI.Common.InputType inputType, System.String title, System.String description, System.Int32 buffer, System.String previous) : System.Boolean`  

```csharp
public abstract System.Boolean ShowVirtualKeyboard(Colossal.PSI.Common.InputType inputType, System.String title, System.String description, System.Int32 buffer, System.String previous);
```


## Events

- `onInputDismissed` : `Colossal.PSI.Common.InputDismissedEventHandler`  

```csharp
public event Colossal.PSI.Common.InputDismissedEventHandler onInputDismissed;
```


