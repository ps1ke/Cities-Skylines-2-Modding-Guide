# Colossal.PSI.Discord.DiscordRichPresence

**Assembly:** `Colossal.PSI.Discord`  
**Namespace:** `Colossal.PSI.Discord`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.PSI.Common.IRichPresenceSupport`, `Colossal.PSI.Common.IPlatformServiceIntegration`, `Colossal.PSI.Common.IDisposableAsync`  

## Fields

- `private System.Boolean m_IsInitialized`  
- `private Discord.Discord m_Discord`  
- `private Discord.ActivityManager m_ActivityManager`  
- `private readonly System.Int64 m_ClientId`  
- `private readonly Colossal.PSI.Common.RateLimitedInvoke m_Limiter`  
- `private Colossal.PSI.Common.OnStatusChangedEventHandler onStatusChanged`  
- `private static Colossal.Logging.ILog log`  

## Properties

- `public System.String name { get }`  
- `public System.Boolean isInitialized { get }`  

## Constructors

- `public DiscordRichPresence(System.Int64 clientId)`  

## Methods

- `public ClearRichPresence() : System.Threading.Tasks.Task`  
- `private Colossal.PSI.Common.IRichPresenceSupport.SetRichPresence(System.String key) : System.Void`  
- `public Dispose(System.Boolean disposeEvents, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  
- `public Initialize(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public LogVersion(System.Text.StringBuilder b) : System.Void`  
- `public SetRichPresence(System.String details, System.String state = null, System.DateTime startTime = null, System.String largeImageKey = null, System.String largeImageText = null, System.String smallImageKey = null, System.String smallImageText = null) : System.Void`  
- `public Update() : System.Void`  
- `private UpdateRichPresence(System.String detailsKey, System.String stateKey = null, System.DateTime startTime = null, System.String largeImageKey = null, System.String largeImageText = null, System.String smallImageKey = null, System.String smallImageText = null) : System.Void`  

## Events

- `onStatusChanged` : `Colossal.PSI.Common.OnStatusChangedEventHandler`  

## Nested types

- `Colossal.PSI.Discord.DiscordRichPresence+<>c`  
- `Colossal.PSI.Discord.DiscordRichPresence+<>c__DisplayClass17_0`  
- `Colossal.PSI.Discord.DiscordRichPresence+<>c__DisplayClass18_0`  
- `Colossal.PSI.Discord.DiscordRichPresence+<>c__DisplayClass20_0`  
- `Colossal.PSI.Discord.DiscordRichPresence+<ClearRichPresence>d__20`  

