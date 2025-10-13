# PDX.ModsUI.ModsUIView

**Assembly:** `PDX.ModsUI`  
**Namespace:** `PDX.ModsUI`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `PDX.ModsUI.IModsUIView`, `System.IDisposable`  

## Code

```csharp
public class ModsUIView : PDX.ModsUI.IModsUIView, System.IDisposable
{
    private System.EventHandler Enabled;
    private System.EventHandler Disabled;
    private System.EventHandler Destroyed;
    private PDX.ModsUI.Adapters.ICohtmlViewAdapter <CohtmlView>k__BackingField;
    private PDX.ModsUI.Adapters.IModsUiVirtualKeyboard <VirtualKeyboard>k__BackingField;
    private System.Action<System.UInt64> <OpenPlayerProfile>k__BackingField;
    private System.Action<System.String> <OpenURL>k__BackingField;
    private System.Action<System.String> <OpenStore>k__BackingField;
    private System.Action<System.String> <CopyToClipboard>k__BackingField;
    private PDX.SDK.Contracts.Util.IDiskIO <DiskIO>k__BackingField;
    private PDX.ModsUI.UITypes.ModsUiUserSettings <ModsUiUserSettings>k__BackingField;
    private System.Func<System.Boolean> <OngoingPleaseWait>k__BackingField;
    private PDX.ModsUI.IModsUI <ModsUI>k__BackingField;
    private PDX.ModsUI.UITypes.FeatureFlags <FeatureFlags>k__BackingField;
    internal static PDX.ModsUI.ModsHostLocations ModsHostLocations;

    public PDX.ModsUI.Adapters.ICohtmlViewAdapter CohtmlView { get; private set; }
    public PDX.ModsUI.Adapters.IModsUiVirtualKeyboard VirtualKeyboard { get; private set; }
    public System.Action<System.UInt64> OpenPlayerProfile { get; set; }
    public System.Action<System.String> OpenURL { get; set; }
    public System.Action<System.String> OpenStore { get; set; }
    public System.Action<System.String> CopyToClipboard { get; set; }
    public PDX.SDK.Contracts.Util.IDiskIO DiskIO { get; set; }
    public PDX.ModsUI.UITypes.ModsUiUserSettings ModsUiUserSettings { get; private set; }
    public System.Func<System.Boolean> OngoingPleaseWait { get; set; }
    internal PDX.ModsUI.IModsUI ModsUI { internal get; private set; }
    internal PDX.ModsUI.UITypes.FeatureFlags FeatureFlags { internal get; private set; }
    public PDX.ModsUI.InputMode InputMode { get; set; }
    public System.Int32 ScrollSpeedMultiplier { get; set; }
    public System.String Language { get; set; }

    public ModsUIView(PDX.ModsUI.Adapters.ICohtmlViewAdapter cohtmlView);
    public ModsUIView(PDX.ModsUI.Adapters.ICohtmlViewAdapter cohtmlView, PDX.ModsUI.Adapters.IModsUiVirtualKeyboard virtualKeyboard);

    public System.Void Dispose();
    public System.Void Hide(System.Boolean destroy);
    public System.Void HidePleaseWait();
    public System.Void Init(PDX.SDK.Contracts.IContext sdkContext, System.String language, PDX.SDK.Contracts.Enums.LogLevel logLevel);
    public System.Void Init(PDX.SDK.Contracts.IContext sdkContext, System.String language, PDX.ModsUI.Services.ILogService logger);
    public System.Void Init(PDX.SDK.Contracts.IContext sdkContext, System.String language, PDX.ModsUI.Services.ILogService logger, PDX.ModsUI.UITypes.FeatureFlags featureFlags);
    private System.Void OngoingWait();
    private System.Void OnReadyForBindings();
    public System.Void Show();
    public System.Void Show(PDX.ModsUI.ModsUIScreen screen);
    public System.Void Show(PDX.ModsUI.ModsUIScreen screen, System.Int32 id);
    public System.Void Show(PDX.ModsUI.ModsUIScreen screen, System.String id);
    public System.Void Show(PDX.ModsUI.ModsUIScreen screen, System.String id, PDX.ModsUI.QueryParameters queryParameters);
    private System.Void Show(PDX.ModsUI.ModsUIScreen screen, System.String id, System.Boolean triggerEvent, PDX.ModsUI.QueryParameters queryParameters);
    public System.Void ShowPleaseWait(System.String title, System.String text);
}
```


## Fields

- `private System.EventHandler Enabled`  

```csharp
private System.EventHandler Enabled;
```

- `private System.EventHandler Disabled`  

```csharp
private System.EventHandler Disabled;
```

- `private System.EventHandler Destroyed`  

```csharp
private System.EventHandler Destroyed;
```

- `private PDX.ModsUI.Adapters.ICohtmlViewAdapter <CohtmlView>k__BackingField`  

```csharp
private PDX.ModsUI.Adapters.ICohtmlViewAdapter <CohtmlView>k__BackingField;
```

- `private PDX.ModsUI.Adapters.IModsUiVirtualKeyboard <VirtualKeyboard>k__BackingField`  

```csharp
private PDX.ModsUI.Adapters.IModsUiVirtualKeyboard <VirtualKeyboard>k__BackingField;
```

- `private System.Action<System.UInt64> <OpenPlayerProfile>k__BackingField`  

```csharp
private System.Action<System.UInt64> <OpenPlayerProfile>k__BackingField;
```

- `private System.Action<System.String> <OpenURL>k__BackingField`  

```csharp
private System.Action<System.String> <OpenURL>k__BackingField;
```

- `private System.Action<System.String> <OpenStore>k__BackingField`  

```csharp
private System.Action<System.String> <OpenStore>k__BackingField;
```

- `private System.Action<System.String> <CopyToClipboard>k__BackingField`  

```csharp
private System.Action<System.String> <CopyToClipboard>k__BackingField;
```

- `private PDX.SDK.Contracts.Util.IDiskIO <DiskIO>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Util.IDiskIO <DiskIO>k__BackingField;
```

- `private PDX.ModsUI.UITypes.ModsUiUserSettings <ModsUiUserSettings>k__BackingField`  

```csharp
private PDX.ModsUI.UITypes.ModsUiUserSettings <ModsUiUserSettings>k__BackingField;
```

- `private System.Func<System.Boolean> <OngoingPleaseWait>k__BackingField`  

```csharp
private System.Func<System.Boolean> <OngoingPleaseWait>k__BackingField;
```

- `private PDX.ModsUI.IModsUI <ModsUI>k__BackingField`  

```csharp
private PDX.ModsUI.IModsUI <ModsUI>k__BackingField;
```

- `private PDX.ModsUI.UITypes.FeatureFlags <FeatureFlags>k__BackingField`  

```csharp
private PDX.ModsUI.UITypes.FeatureFlags <FeatureFlags>k__BackingField;
```

- `internal static PDX.ModsUI.ModsHostLocations ModsHostLocations`  

```csharp
internal static PDX.ModsUI.ModsHostLocations ModsHostLocations;
```


## Properties

- `public PDX.ModsUI.Adapters.ICohtmlViewAdapter CohtmlView { get; private set }`  

```csharp
public PDX.ModsUI.Adapters.ICohtmlViewAdapter CohtmlView { get; private set; }
```

- `public PDX.ModsUI.Adapters.IModsUiVirtualKeyboard VirtualKeyboard { get; private set }`  

```csharp
public PDX.ModsUI.Adapters.IModsUiVirtualKeyboard VirtualKeyboard { get; private set; }
```

- `public System.Action<System.UInt64> OpenPlayerProfile { get; set }`  

```csharp
public System.Action<System.UInt64> OpenPlayerProfile { get; set; }
```

- `public System.Action<System.String> OpenURL { get; set }`  

```csharp
public System.Action<System.String> OpenURL { get; set; }
```

- `public System.Action<System.String> OpenStore { get; set }`  

```csharp
public System.Action<System.String> OpenStore { get; set; }
```

- `public System.Action<System.String> CopyToClipboard { get; set }`  

```csharp
public System.Action<System.String> CopyToClipboard { get; set; }
```

- `public PDX.SDK.Contracts.Util.IDiskIO DiskIO { get; set }`  

```csharp
public PDX.SDK.Contracts.Util.IDiskIO DiskIO { get; set; }
```

- `public PDX.ModsUI.UITypes.ModsUiUserSettings ModsUiUserSettings { get; private set }`  

```csharp
public PDX.ModsUI.UITypes.ModsUiUserSettings ModsUiUserSettings { get; private set; }
```

- `public System.Func<System.Boolean> OngoingPleaseWait { get; set }`  

```csharp
public System.Func<System.Boolean> OngoingPleaseWait { get; set; }
```

- `internal PDX.ModsUI.IModsUI ModsUI { internal get; private set }`  

```csharp
internal PDX.ModsUI.IModsUI ModsUI { internal get; private set; }
```

- `internal PDX.ModsUI.UITypes.FeatureFlags FeatureFlags { internal get; private set }`  

```csharp
internal PDX.ModsUI.UITypes.FeatureFlags FeatureFlags { internal get; private set; }
```

- `public PDX.ModsUI.InputMode InputMode { get; set }`  

```csharp
public PDX.ModsUI.InputMode InputMode { get; set; }
```

- `public System.Int32 ScrollSpeedMultiplier { get; set }`  

```csharp
public System.Int32 ScrollSpeedMultiplier { get; set; }
```

- `public System.String Language { get; set }`  

```csharp
public System.String Language { get; set; }
```


## Constructors

- `public ModsUIView(PDX.ModsUI.Adapters.ICohtmlViewAdapter cohtmlView)`  

```csharp
public ModsUIView(PDX.ModsUI.Adapters.ICohtmlViewAdapter cohtmlView);
```

- `public ModsUIView(PDX.ModsUI.Adapters.ICohtmlViewAdapter cohtmlView, PDX.ModsUI.Adapters.IModsUiVirtualKeyboard virtualKeyboard)`  

```csharp
public ModsUIView(PDX.ModsUI.Adapters.ICohtmlViewAdapter cohtmlView, PDX.ModsUI.Adapters.IModsUiVirtualKeyboard virtualKeyboard);
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public Hide(System.Boolean destroy = False) : System.Void`  

```csharp
public System.Void Hide(System.Boolean destroy);
```

- `public HidePleaseWait() : System.Void`  

```csharp
public System.Void HidePleaseWait();
```

- `public Init(PDX.SDK.Contracts.IContext sdkContext, System.String language = en, PDX.SDK.Contracts.Enums.LogLevel logLevel = L2_Warning) : System.Void`  

```csharp
public System.Void Init(PDX.SDK.Contracts.IContext sdkContext, System.String language, PDX.SDK.Contracts.Enums.LogLevel logLevel);
```

- `public Init(PDX.SDK.Contracts.IContext sdkContext, System.String language, PDX.ModsUI.Services.ILogService logger) : System.Void`  

```csharp
public System.Void Init(PDX.SDK.Contracts.IContext sdkContext, System.String language, PDX.ModsUI.Services.ILogService logger);
```

- `public Init(PDX.SDK.Contracts.IContext sdkContext, System.String language, PDX.ModsUI.Services.ILogService logger, PDX.ModsUI.UITypes.FeatureFlags featureFlags) : System.Void`  

```csharp
public System.Void Init(PDX.SDK.Contracts.IContext sdkContext, System.String language, PDX.ModsUI.Services.ILogService logger, PDX.ModsUI.UITypes.FeatureFlags featureFlags);
```

- `private OngoingWait() : System.Void`  

```csharp
private System.Void OngoingWait();
```

- `private OnReadyForBindings() : System.Void`  

```csharp
private System.Void OnReadyForBindings();
```

- `public Show() : System.Void`  

```csharp
public System.Void Show();
```

- `public Show(PDX.ModsUI.ModsUIScreen screen) : System.Void`  

```csharp
public System.Void Show(PDX.ModsUI.ModsUIScreen screen);
```

- `public Show(PDX.ModsUI.ModsUIScreen screen, System.Int32 id) : System.Void`  

```csharp
public System.Void Show(PDX.ModsUI.ModsUIScreen screen, System.Int32 id);
```

- `public Show(PDX.ModsUI.ModsUIScreen screen, System.String id) : System.Void`  

```csharp
public System.Void Show(PDX.ModsUI.ModsUIScreen screen, System.String id);
```

- `public Show(PDX.ModsUI.ModsUIScreen screen, System.String id, PDX.ModsUI.QueryParameters queryParameters) : System.Void`  

```csharp
public System.Void Show(PDX.ModsUI.ModsUIScreen screen, System.String id, PDX.ModsUI.QueryParameters queryParameters);
```

- `private Show(PDX.ModsUI.ModsUIScreen screen, System.String id, System.Boolean triggerEvent, PDX.ModsUI.QueryParameters queryParameters = null) : System.Void`  

```csharp
private System.Void Show(PDX.ModsUI.ModsUIScreen screen, System.String id, System.Boolean triggerEvent, PDX.ModsUI.QueryParameters queryParameters);
```

- `public ShowPleaseWait(System.String title = , System.String text = ) : System.Void`  

```csharp
public System.Void ShowPleaseWait(System.String title, System.String text);
```


## Events

- `Enabled` : `System.EventHandler`  

```csharp
public event System.EventHandler Enabled;
```

- `Disabled` : `System.EventHandler`  

```csharp
public event System.EventHandler Disabled;
```

- `Destroyed` : `System.EventHandler`  

```csharp
public event System.EventHandler Destroyed;
```


## Nested types

- `PDX.ModsUI.ModsUIView+<>c`  
- `PDX.ModsUI.ModsUIView+<OngoingWait>d__71`  

