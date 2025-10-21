# Game.PSI.PdxSdk.PdxModsUI

**Assembly:** `Game`  
**Namespace:** `Game.PSI.PdxSdk`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.PSI.PdxSdk.IPdxModsUI`, `System.IDisposable`  

## Code

```csharp
public class PdxModsUI : Colossal.PSI.PdxSdk.IPdxModsUI, System.IDisposable
{
    private Colossal.PSI.PdxSdk.PdxSdkPlatform m_PdxPlatform;
    private static Colossal.Logging.ILog log;
    private static readonly System.String kModsUIHost;
    private static readonly System.String kModsUIUri;

    public Colossal.PSI.PdxSdk.PdxSdkPlatform platform { get; }
    public System.String locale { get; }
    public PDX.ModsUI.Adapters.ICohtmlViewAdapter uiViewAdapter { get; }
    public PDX.ModsUI.Services.ILogService logger { get; }
    public System.Boolean isActive { get; }

    public PdxModsUI();

    private System.Void <.ctor>b__8_0(Colossal.PSI.Common.IPlatformServiceIntegration psi);
    public System.Void Destroy();
    public System.Void Dispose();
    public PDX.ModsUI.InputMode GetInputMode();
    private System.Void OnActiveDeviceChanged(UnityEngine.InputSystem.InputDevice newDevice, UnityEngine.InputSystem.InputDevice oldDevice, System.Boolean schemeChanged);
    public System.Void Show();
    private System.Void UpdateLocale();
}
```


## Fields

- `private Colossal.PSI.PdxSdk.PdxSdkPlatform m_PdxPlatform`  

```csharp
private Colossal.PSI.PdxSdk.PdxSdkPlatform m_PdxPlatform;
```

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```

- `private static readonly System.String kModsUIHost`  

```csharp
private static readonly System.String kModsUIHost;
```

- `private static readonly System.String kModsUIUri`  

```csharp
private static readonly System.String kModsUIUri;
```


## Properties

- `public Colossal.PSI.PdxSdk.PdxSdkPlatform platform { get }`  

```csharp
public Colossal.PSI.PdxSdk.PdxSdkPlatform platform { get; }
```

- `public System.String locale { get }`  

```csharp
public System.String locale { get; }
```

- `public PDX.ModsUI.Adapters.ICohtmlViewAdapter uiViewAdapter { get }`  

```csharp
public PDX.ModsUI.Adapters.ICohtmlViewAdapter uiViewAdapter { get; }
```

- `public PDX.ModsUI.Services.ILogService logger { get }`  

```csharp
public PDX.ModsUI.Services.ILogService logger { get; }
```

- `public System.Boolean isActive { get }`  

```csharp
public System.Boolean isActive { get; }
```


## Constructors

- `public PdxModsUI()`  

```csharp
public PdxModsUI();
```


## Methods

- `private <.ctor>b__8_0(Colossal.PSI.Common.IPlatformServiceIntegration psi) : System.Void`  

```csharp
private System.Void <.ctor>b__8_0(Colossal.PSI.Common.IPlatformServiceIntegration psi);
```

- `public Destroy() : System.Void`  

```csharp
public System.Void Destroy();
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public GetInputMode() : PDX.ModsUI.InputMode`  

```csharp
public PDX.ModsUI.InputMode GetInputMode();
```

- `private OnActiveDeviceChanged(UnityEngine.InputSystem.InputDevice newDevice, UnityEngine.InputSystem.InputDevice oldDevice, System.Boolean schemeChanged) : System.Void`  

```csharp
private System.Void OnActiveDeviceChanged(UnityEngine.InputSystem.InputDevice newDevice, UnityEngine.InputSystem.InputDevice oldDevice, System.Boolean schemeChanged);
```

- `public Show() : System.Void`  

```csharp
public System.Void Show();
```

- `private UpdateLocale() : System.Void`  

```csharp
private System.Void UpdateLocale();
```


## Nested types

- `Game.PSI.PdxSdk.PdxModsUI+ColossalUIViewAdapter`  
- `Game.PSI.PdxSdk.PdxModsUI+ModsUILogger`  

