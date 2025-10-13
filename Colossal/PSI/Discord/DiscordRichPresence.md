# Colossal.PSI.Discord.DiscordRichPresence

**Assembly:** `Colossal.PSI.Discord`  
**Namespace:** `Colossal.PSI.Discord`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.PSI.Common.IRichPresenceSupport`, `Colossal.PSI.Common.IPlatformServiceIntegration`, `Colossal.PSI.Common.IDisposableAsync`  

## Code

```csharp
public class DiscordRichPresence : Colossal.PSI.Common.IRichPresenceSupport, Colossal.PSI.Common.IPlatformServiceIntegration, Colossal.PSI.Common.IDisposableAsync
{
    private System.Boolean m_IsInitialized;
    private Discord.Discord m_Discord;
    private Discord.ActivityManager m_ActivityManager;
    private readonly System.Int64 m_ClientId;
    private readonly Colossal.PSI.Common.RateLimitedInvoke m_Limiter;
    private Colossal.PSI.Common.OnStatusChangedEventHandler onStatusChanged;
    private static Colossal.Logging.ILog log;

    public System.String name { get; }
    public System.Boolean isInitialized { get; }

    public DiscordRichPresence(System.Int64 clientId);

    public System.Threading.Tasks.Task ClearRichPresence();
    private System.Void Colossal.PSI.Common.IRichPresenceSupport.SetRichPresence(System.String key);
    public System.Threading.Tasks.Task Dispose(System.Boolean disposeEvents, System.Threading.CancellationToken token);
    public System.Threading.Tasks.Task<System.Boolean> Initialize(System.Threading.CancellationToken token);
    public System.Void LogVersion(System.Text.StringBuilder b);
    public System.Void SetRichPresence(System.String details, System.String state, System.DateTime startTime, System.String largeImageKey, System.String largeImageText, System.String smallImageKey, System.String smallImageText);
    public System.Void Update();
    private System.Void UpdateRichPresence(System.String detailsKey, System.String stateKey, System.DateTime startTime, System.String largeImageKey, System.String largeImageText, System.String smallImageKey, System.String smallImageText);
}
```


## Fields

- `private System.Boolean m_IsInitialized`  

```csharp
private System.Boolean m_IsInitialized;
```

- `private Discord.Discord m_Discord`  

```csharp
private Discord.Discord m_Discord;
```

- `private Discord.ActivityManager m_ActivityManager`  

```csharp
private Discord.ActivityManager m_ActivityManager;
```

- `private readonly System.Int64 m_ClientId`  

```csharp
private readonly System.Int64 m_ClientId;
```

- `private readonly Colossal.PSI.Common.RateLimitedInvoke m_Limiter`  

```csharp
private readonly Colossal.PSI.Common.RateLimitedInvoke m_Limiter;
```

- `private Colossal.PSI.Common.OnStatusChangedEventHandler onStatusChanged`  

```csharp
private Colossal.PSI.Common.OnStatusChangedEventHandler onStatusChanged;
```

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```


## Properties

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public System.Boolean isInitialized { get }`  

```csharp
public System.Boolean isInitialized { get; }
```


## Constructors

- `public DiscordRichPresence(System.Int64 clientId)`  

```csharp
public DiscordRichPresence(System.Int64 clientId);
```


## Methods

- `public ClearRichPresence() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task ClearRichPresence();
```

- `private Colossal.PSI.Common.IRichPresenceSupport.SetRichPresence(System.String key) : System.Void`  

```csharp
private System.Void Colossal.PSI.Common.IRichPresenceSupport.SetRichPresence(System.String key);
```

- `public Dispose(System.Boolean disposeEvents, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task Dispose(System.Boolean disposeEvents, System.Threading.CancellationToken token);
```

- `public Initialize(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public System.Threading.Tasks.Task<System.Boolean> Initialize(System.Threading.CancellationToken token);
```

- `public LogVersion(System.Text.StringBuilder b) : System.Void`  

```csharp
public System.Void LogVersion(System.Text.StringBuilder b);
```

- `public SetRichPresence(System.String details, System.String state = null, System.DateTime startTime = null, System.String largeImageKey = null, System.String largeImageText = null, System.String smallImageKey = null, System.String smallImageText = null) : System.Void`  

```csharp
public System.Void SetRichPresence(System.String details, System.String state, System.DateTime startTime, System.String largeImageKey, System.String largeImageText, System.String smallImageKey, System.String smallImageText);
```

- `public Update() : System.Void`  

```csharp
public System.Void Update();
```

- `private UpdateRichPresence(System.String detailsKey, System.String stateKey = null, System.DateTime startTime = null, System.String largeImageKey = null, System.String largeImageText = null, System.String smallImageKey = null, System.String smallImageText = null) : System.Void`  

```csharp
private System.Void UpdateRichPresence(System.String detailsKey, System.String stateKey, System.DateTime startTime, System.String largeImageKey, System.String largeImageText, System.String smallImageKey, System.String smallImageText);
```


## Events

- `onStatusChanged` : `Colossal.PSI.Common.OnStatusChangedEventHandler`  

```csharp
public event Colossal.PSI.Common.OnStatusChangedEventHandler onStatusChanged;
```


## Nested types

- `Colossal.PSI.Discord.DiscordRichPresence+<>c`  
- `Colossal.PSI.Discord.DiscordRichPresence+<>c__DisplayClass17_0`  
- `Colossal.PSI.Discord.DiscordRichPresence+<>c__DisplayClass18_0`  
- `Colossal.PSI.Discord.DiscordRichPresence+<>c__DisplayClass20_0`  
- `Colossal.PSI.Discord.DiscordRichPresence+<ClearRichPresence>d__20`  

