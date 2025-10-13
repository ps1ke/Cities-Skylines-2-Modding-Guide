# PDX.ModsUI.IModsUIView

**Assembly:** `PDX.ModsUI`  
**Namespace:** `PDX.ModsUI`  

**Type:** interface abstract public  

**Implements:** `System.IDisposable`  

## Code

```csharp
public abstract interface IModsUIView : System.IDisposable
{
    public System.String Language { get; set; }
    public PDX.ModsUI.InputMode InputMode { get; set; }
    public PDX.ModsUI.Adapters.ICohtmlViewAdapter CohtmlView { get; }
    public PDX.ModsUI.Adapters.IModsUiVirtualKeyboard VirtualKeyboard { get; }
    public System.Action<System.String> OpenURL { get; set; }
    public System.Action<System.String> CopyToClipboard { get; set; }
    public System.Action<System.UInt64> OpenPlayerProfile { get; set; }
    public System.Action<System.String> OpenStore { get; set; }
    public PDX.SDK.Contracts.Util.IDiskIO DiskIO { get; set; }
    public PDX.ModsUI.UITypes.ModsUiUserSettings ModsUiUserSettings { get; }

    public abstract System.Void Hide(System.Boolean destroy);
    public abstract System.Void Init(PDX.SDK.Contracts.IContext sdkContext, System.String language, PDX.SDK.Contracts.Enums.LogLevel logLevel);
    public abstract System.Void Init(PDX.SDK.Contracts.IContext sdkContext, System.String language, PDX.ModsUI.Services.ILogService logger);
    public abstract System.Void Init(PDX.SDK.Contracts.IContext sdkContext, System.String language, PDX.ModsUI.Services.ILogService logger, PDX.ModsUI.UITypes.FeatureFlags featureFlags);
    public abstract System.Void Show();
}
```


## Properties

- `public System.String Language { get; set }`  

```csharp
public System.String Language { get; set; }
```

- `public PDX.ModsUI.InputMode InputMode { get; set }`  

```csharp
public PDX.ModsUI.InputMode InputMode { get; set; }
```

- `public PDX.ModsUI.Adapters.ICohtmlViewAdapter CohtmlView { get }`  

```csharp
public PDX.ModsUI.Adapters.ICohtmlViewAdapter CohtmlView { get; }
```

- `public PDX.ModsUI.Adapters.IModsUiVirtualKeyboard VirtualKeyboard { get }`  

```csharp
public PDX.ModsUI.Adapters.IModsUiVirtualKeyboard VirtualKeyboard { get; }
```

- `public System.Action<System.String> OpenURL { get; set }`  

```csharp
public System.Action<System.String> OpenURL { get; set; }
```

- `public System.Action<System.String> CopyToClipboard { get; set }`  

```csharp
public System.Action<System.String> CopyToClipboard { get; set; }
```

- `public System.Action<System.UInt64> OpenPlayerProfile { get; set }`  

```csharp
public System.Action<System.UInt64> OpenPlayerProfile { get; set; }
```

- `public System.Action<System.String> OpenStore { get; set }`  

```csharp
public System.Action<System.String> OpenStore { get; set; }
```

- `public PDX.SDK.Contracts.Util.IDiskIO DiskIO { get; set }`  

```csharp
public PDX.SDK.Contracts.Util.IDiskIO DiskIO { get; set; }
```

- `public PDX.ModsUI.UITypes.ModsUiUserSettings ModsUiUserSettings { get }`  

```csharp
public PDX.ModsUI.UITypes.ModsUiUserSettings ModsUiUserSettings { get; }
```


## Methods

- `public abstract Hide(System.Boolean destroy = False) : System.Void`  

```csharp
public abstract System.Void Hide(System.Boolean destroy);
```

- `public abstract Init(PDX.SDK.Contracts.IContext sdkContext, System.String language, PDX.SDK.Contracts.Enums.LogLevel logLevel) : System.Void`  

```csharp
public abstract System.Void Init(PDX.SDK.Contracts.IContext sdkContext, System.String language, PDX.SDK.Contracts.Enums.LogLevel logLevel);
```

- `public abstract Init(PDX.SDK.Contracts.IContext sdkContext, System.String language, PDX.ModsUI.Services.ILogService logger) : System.Void`  

```csharp
public abstract System.Void Init(PDX.SDK.Contracts.IContext sdkContext, System.String language, PDX.ModsUI.Services.ILogService logger);
```

- `public abstract Init(PDX.SDK.Contracts.IContext sdkContext, System.String language, PDX.ModsUI.Services.ILogService logger, PDX.ModsUI.UITypes.FeatureFlags featureFlags) : System.Void`  

```csharp
public abstract System.Void Init(PDX.SDK.Contracts.IContext sdkContext, System.String language, PDX.ModsUI.Services.ILogService logger, PDX.ModsUI.UITypes.FeatureFlags featureFlags);
```

- `public abstract Show() : System.Void`  

```csharp
public abstract System.Void Show();
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


