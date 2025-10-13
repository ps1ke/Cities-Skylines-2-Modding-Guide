# PDX.SDK.Contracts.Configuration.TelemetryConfig

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Configuration`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class TelemetryConfig
{
    private System.Nullable<System.Boolean> <StandardTelemetryEnabled>k__BackingField;
    private System.Nullable<System.Boolean> <TelemetryDebugEnabled>k__BackingField;
    private System.Nullable<System.Boolean> <UnityEventTelemetryEnable>k__BackingField;
    private System.Nullable<System.Boolean> <SkipLegalChecksAndEnableTelemetry>k__BackingField;
    public static const System.Boolean DefaultStateTelemetryConsent;

    public System.Nullable<System.Boolean> StandardTelemetryEnabled { get; set; }
    public System.Nullable<System.Boolean> TelemetryDebugEnabled { get; set; }
    public System.Nullable<System.Boolean> UnityEventTelemetryEnable { get; set; }
    public System.Nullable<System.Boolean> SkipLegalChecksAndEnableTelemetry { get; set; }

    public TelemetryConfig();

    public System.Void SetIfNotNull(PDX.SDK.Contracts.Configuration.TelemetryConfig cfg);
}
```


## Fields

- `private System.Nullable<System.Boolean> <StandardTelemetryEnabled>k__BackingField`  

```csharp
private System.Nullable<System.Boolean> <StandardTelemetryEnabled>k__BackingField;
```

- `private System.Nullable<System.Boolean> <TelemetryDebugEnabled>k__BackingField`  

```csharp
private System.Nullable<System.Boolean> <TelemetryDebugEnabled>k__BackingField;
```

- `private System.Nullable<System.Boolean> <UnityEventTelemetryEnable>k__BackingField`  

```csharp
private System.Nullable<System.Boolean> <UnityEventTelemetryEnable>k__BackingField;
```

- `private System.Nullable<System.Boolean> <SkipLegalChecksAndEnableTelemetry>k__BackingField`  

```csharp
private System.Nullable<System.Boolean> <SkipLegalChecksAndEnableTelemetry>k__BackingField;
```

- `public static const System.Boolean DefaultStateTelemetryConsent`  

```csharp
public static const System.Boolean DefaultStateTelemetryConsent;
```


## Properties

- `public System.Nullable<System.Boolean> StandardTelemetryEnabled { get; set }`  

```csharp
public System.Nullable<System.Boolean> StandardTelemetryEnabled { get; set; }
```

- `public System.Nullable<System.Boolean> TelemetryDebugEnabled { get; set }`  

```csharp
public System.Nullable<System.Boolean> TelemetryDebugEnabled { get; set; }
```

- `public System.Nullable<System.Boolean> UnityEventTelemetryEnable { get; set }`  

```csharp
public System.Nullable<System.Boolean> UnityEventTelemetryEnable { get; set; }
```

- `public System.Nullable<System.Boolean> SkipLegalChecksAndEnableTelemetry { get; set }`  

```csharp
public System.Nullable<System.Boolean> SkipLegalChecksAndEnableTelemetry { get; set; }
```


## Constructors

- `public TelemetryConfig()`  

```csharp
public TelemetryConfig();
```


## Methods

- `public SetIfNotNull(PDX.SDK.Contracts.Configuration.TelemetryConfig cfg) : System.Void`  

```csharp
public System.Void SetIfNotNull(PDX.SDK.Contracts.Configuration.TelemetryConfig cfg);
```


