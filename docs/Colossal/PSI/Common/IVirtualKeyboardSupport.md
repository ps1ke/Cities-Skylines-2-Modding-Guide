# Colossal.PSI.Common.IVirtualKeyboardSupport

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** interface abstract public  

**Implements:** `Colossal.PSI.Common.IPlatformServiceIntegration`, `Colossal.PSI.Common.IDisposableAsync`  

## Properties

- `public System.Boolean passThroughVKeyboard { get }`  

## Methods

- `public abstract DismissVirtualKeyboard() : System.Void`  
- `public abstract SetActiveTextFieldRect(System.Int32 x, System.Int32 y, System.Int32 width, System.Int32 height) : System.Void`  
- `public abstract ShowVirtualKeyboard(Colossal.PSI.Common.InputType inputType, System.String title, System.String description, System.Int32 buffer, System.String previous) : System.Boolean`  

## Events

- `onInputDismissed` : `Colossal.PSI.Common.InputDismissedEventHandler`  

