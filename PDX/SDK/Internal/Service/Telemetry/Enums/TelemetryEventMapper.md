# PDX.SDK.Internal.Service.Telemetry.Enums.TelemetryEventMapper

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Internal.Service.Telemetry.Enums`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class TelemetryEventMapper
{
    private static readonly System.Collections.Generic.Dictionary<PDX.SDK.Internal.Service.Telemetry.Enums.StandardTelemetryCall, System.String> EventNames;

    public static System.String GetEventName(PDX.SDK.Internal.Service.Telemetry.Enums.StandardTelemetryCall call);
}
```


## Fields

- `private static readonly System.Collections.Generic.Dictionary<PDX.SDK.Internal.Service.Telemetry.Enums.StandardTelemetryCall, System.String> EventNames`  

```csharp
private static readonly System.Collections.Generic.Dictionary<PDX.SDK.Internal.Service.Telemetry.Enums.StandardTelemetryCall, System.String> EventNames;
```


## Methods

- `public static GetEventName(PDX.SDK.Internal.Service.Telemetry.Enums.StandardTelemetryCall call) : System.String`  

```csharp
public static System.String GetEventName(PDX.SDK.Internal.Service.Telemetry.Enums.StandardTelemetryCall call);
```


