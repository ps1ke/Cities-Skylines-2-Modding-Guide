# Game.PSI.PdxSdk.PdxModsUI

**Assembly:** `Game`  
**Namespace:** `Game.PSI.PdxSdk`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.PSI.PdxSdk.IPdxModsUI`, `System.IDisposable`  

## Fields

- `private Colossal.PSI.PdxSdk.PdxSdkPlatform m_PdxPlatform`  
- `private static Colossal.Logging.ILog log`  
- `private static readonly System.String kModsUIHost`  
- `private static readonly System.String kModsUIUri`  

## Properties

- `public Colossal.PSI.PdxSdk.PdxSdkPlatform platform { get }`  
- `public System.String locale { get }`  
- `public PDX.ModsUI.Adapters.ICohtmlViewAdapter uiViewAdapter { get }`  
- `public PDX.ModsUI.Services.ILogService logger { get }`  
- `public System.Boolean isActive { get }`  

## Constructors

- `public PdxModsUI()`  

## Methods

- `private <.ctor>b__8_0(Colossal.PSI.Common.IPlatformServiceIntegration psi) : System.Void`  
- `public Destroy() : System.Void`  
- `public Dispose() : System.Void`  
- `public GetInputMode() : PDX.ModsUI.InputMode`  
- `private OnActiveDeviceChanged(UnityEngine.InputSystem.InputDevice newDevice, UnityEngine.InputSystem.InputDevice oldDevice, System.Boolean schemeChanged) : System.Void`  
- `public Show() : System.Void`  
- `private UpdateLocale() : System.Void`  

## Nested types

- `Game.PSI.PdxSdk.PdxModsUI+ColossalUIViewAdapter`  
- `Game.PSI.PdxSdk.PdxModsUI+ModsUILogger`  

