# PDX.SDK.Contracts.Configuration.Config

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Configuration`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class Config
{
    private System.Nullable<PDX.SDK.Contracts.Enums.BackendEnvironment> <Environment>k__BackingField;
    private System.String <GameVersion>k__BackingField;
    private System.String <GameChecksum>k__BackingField;
    private System.Nullable<PDX.SDK.Contracts.Enums.Ecosystem> <Ecosystem>k__BackingField;
    private System.String <UserIdType>k__BackingField;
    private System.String <UserId>k__BackingField;
    private System.Nullable<PDX.SDK.Contracts.Enums.LogLevel> <LogLevel>k__BackingField;
    private PDX.SDK.Contracts.Logging.ILogger <Logger>k__BackingField;
    private System.String <DiskIORoot>k__BackingField;
    private PDX.SDK.Contracts.Util.IDiskIO <DiskIOHandler>k__BackingField;
    private System.Nullable<System.Int32> <ChunkSize>k__BackingField;
    private System.Nullable<PDX.SDK.Contracts.Enums.Language> <Language>k__BackingField;
    private System.Collections.Generic.Dictionary<System.String, System.String> <DefaultHeaders>k__BackingField;
    private PDX.SDK.Contracts.Configuration.ThirdParty.ThirdPartyConfig <ThirdParty>k__BackingField;
    private PDX.SDK.Contracts.Configuration.CloudSavesConfig <CloudSaves>k__BackingField;
    private PDX.SDK.Contracts.Configuration.ModsConfig <Mods>k__BackingField;
    private PDX.SDK.Contracts.Configuration.TelemetryConfig <Telemetry>k__BackingField;

    public System.Nullable<PDX.SDK.Contracts.Enums.BackendEnvironment> Environment { get; set; }
    public System.String GameVersion { get; set; }
    public System.String GameChecksum { get; set; }
    public System.Nullable<PDX.SDK.Contracts.Enums.Ecosystem> Ecosystem { get; set; }
    public System.String UserIdType { get; set; }
    public System.String UserId { get; set; }
    public System.Nullable<PDX.SDK.Contracts.Enums.LogLevel> LogLevel { get; set; }
    public PDX.SDK.Contracts.Logging.ILogger Logger { get; set; }
    public System.String DiskIORoot { get; set; }
    public PDX.SDK.Contracts.Util.IDiskIO DiskIOHandler { get; set; }
    public System.Nullable<System.Int32> ChunkSize { get; set; }
    public System.Nullable<PDX.SDK.Contracts.Enums.Language> Language { get; set; }
    public System.Collections.Generic.Dictionary<System.String, System.String> DefaultHeaders { get; set; }
    public PDX.SDK.Contracts.Configuration.ThirdParty.ThirdPartyConfig ThirdParty { get; set; }
    public PDX.SDK.Contracts.Configuration.CloudSavesConfig CloudSaves { get; set; }
    public PDX.SDK.Contracts.Configuration.ModsConfig Mods { get; set; }
    public PDX.SDK.Contracts.Configuration.TelemetryConfig Telemetry { get; set; }

    public Config();

    public System.Void SetDefaultConfigValues();
    public System.Void SetIfNotNull(PDX.SDK.Contracts.Configuration.Config cfg);
}
```


## Fields

- `private System.Nullable<PDX.SDK.Contracts.Enums.BackendEnvironment> <Environment>k__BackingField`  

```csharp
private System.Nullable<PDX.SDK.Contracts.Enums.BackendEnvironment> <Environment>k__BackingField;
```

- `private System.String <GameVersion>k__BackingField`  

```csharp
private System.String <GameVersion>k__BackingField;
```

- `private System.String <GameChecksum>k__BackingField`  

```csharp
private System.String <GameChecksum>k__BackingField;
```

- `private System.Nullable<PDX.SDK.Contracts.Enums.Ecosystem> <Ecosystem>k__BackingField`  

```csharp
private System.Nullable<PDX.SDK.Contracts.Enums.Ecosystem> <Ecosystem>k__BackingField;
```

- `private System.String <UserIdType>k__BackingField`  

```csharp
private System.String <UserIdType>k__BackingField;
```

- `private System.String <UserId>k__BackingField`  

```csharp
private System.String <UserId>k__BackingField;
```

- `private System.Nullable<PDX.SDK.Contracts.Enums.LogLevel> <LogLevel>k__BackingField`  

```csharp
private System.Nullable<PDX.SDK.Contracts.Enums.LogLevel> <LogLevel>k__BackingField;
```

- `private PDX.SDK.Contracts.Logging.ILogger <Logger>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Logging.ILogger <Logger>k__BackingField;
```

- `private System.String <DiskIORoot>k__BackingField`  

```csharp
private System.String <DiskIORoot>k__BackingField;
```

- `private PDX.SDK.Contracts.Util.IDiskIO <DiskIOHandler>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Util.IDiskIO <DiskIOHandler>k__BackingField;
```

- `private System.Nullable<System.Int32> <ChunkSize>k__BackingField`  

```csharp
private System.Nullable<System.Int32> <ChunkSize>k__BackingField;
```

- `private System.Nullable<PDX.SDK.Contracts.Enums.Language> <Language>k__BackingField`  

```csharp
private System.Nullable<PDX.SDK.Contracts.Enums.Language> <Language>k__BackingField;
```

- `private System.Collections.Generic.Dictionary<System.String, System.String> <DefaultHeaders>k__BackingField`  

```csharp
private System.Collections.Generic.Dictionary<System.String, System.String> <DefaultHeaders>k__BackingField;
```

- `private PDX.SDK.Contracts.Configuration.ThirdParty.ThirdPartyConfig <ThirdParty>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Configuration.ThirdParty.ThirdPartyConfig <ThirdParty>k__BackingField;
```

- `private PDX.SDK.Contracts.Configuration.CloudSavesConfig <CloudSaves>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Configuration.CloudSavesConfig <CloudSaves>k__BackingField;
```

- `private PDX.SDK.Contracts.Configuration.ModsConfig <Mods>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Configuration.ModsConfig <Mods>k__BackingField;
```

- `private PDX.SDK.Contracts.Configuration.TelemetryConfig <Telemetry>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Configuration.TelemetryConfig <Telemetry>k__BackingField;
```


## Properties

- `public System.Nullable<PDX.SDK.Contracts.Enums.BackendEnvironment> Environment { get; set }`  

```csharp
public System.Nullable<PDX.SDK.Contracts.Enums.BackendEnvironment> Environment { get; set; }
```

- `public System.String GameVersion { get; set }`  

```csharp
public System.String GameVersion { get; set; }
```

- `public System.String GameChecksum { get; set }`  

```csharp
public System.String GameChecksum { get; set; }
```

- `public System.Nullable<PDX.SDK.Contracts.Enums.Ecosystem> Ecosystem { get; set }`  

```csharp
public System.Nullable<PDX.SDK.Contracts.Enums.Ecosystem> Ecosystem { get; set; }
```

- `public System.String UserIdType { get; set }`  

```csharp
public System.String UserIdType { get; set; }
```

- `public System.String UserId { get; set }`  

```csharp
public System.String UserId { get; set; }
```

- `public System.Nullable<PDX.SDK.Contracts.Enums.LogLevel> LogLevel { get; set }`  

```csharp
public System.Nullable<PDX.SDK.Contracts.Enums.LogLevel> LogLevel { get; set; }
```

- `public PDX.SDK.Contracts.Logging.ILogger Logger { get; set }`  

```csharp
public PDX.SDK.Contracts.Logging.ILogger Logger { get; set; }
```

- `public System.String DiskIORoot { get; set }`  

```csharp
public System.String DiskIORoot { get; set; }
```

- `public PDX.SDK.Contracts.Util.IDiskIO DiskIOHandler { get; set }`  

```csharp
public PDX.SDK.Contracts.Util.IDiskIO DiskIOHandler { get; set; }
```

- `public System.Nullable<System.Int32> ChunkSize { get; set }`  

```csharp
public System.Nullable<System.Int32> ChunkSize { get; set; }
```

- `public System.Nullable<PDX.SDK.Contracts.Enums.Language> Language { get; set }`  

```csharp
public System.Nullable<PDX.SDK.Contracts.Enums.Language> Language { get; set; }
```

- `public System.Collections.Generic.Dictionary<System.String, System.String> DefaultHeaders { get; set }`  

```csharp
public System.Collections.Generic.Dictionary<System.String, System.String> DefaultHeaders { get; set; }
```

- `public PDX.SDK.Contracts.Configuration.ThirdParty.ThirdPartyConfig ThirdParty { get; set }`  

```csharp
public PDX.SDK.Contracts.Configuration.ThirdParty.ThirdPartyConfig ThirdParty { get; set; }
```

- `public PDX.SDK.Contracts.Configuration.CloudSavesConfig CloudSaves { get; set }`  

```csharp
public PDX.SDK.Contracts.Configuration.CloudSavesConfig CloudSaves { get; set; }
```

- `public PDX.SDK.Contracts.Configuration.ModsConfig Mods { get; set }`  

```csharp
public PDX.SDK.Contracts.Configuration.ModsConfig Mods { get; set; }
```

- `public PDX.SDK.Contracts.Configuration.TelemetryConfig Telemetry { get; set }`  

```csharp
public PDX.SDK.Contracts.Configuration.TelemetryConfig Telemetry { get; set; }
```


## Constructors

- `public Config()`  

```csharp
public Config();
```


## Methods

- `public SetDefaultConfigValues() : System.Void`  

```csharp
public System.Void SetDefaultConfigValues();
```

- `public SetIfNotNull(PDX.SDK.Contracts.Configuration.Config cfg) : System.Void`  

```csharp
public System.Void SetIfNotNull(PDX.SDK.Contracts.Configuration.Config cfg);
```


