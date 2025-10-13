# PDX.SDK.Util.TelemetryBuilderExtensions

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Util`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class TelemetryBuilderExtensions
{
    internal static System.Collections.Generic.List<PDX.SDK.Contracts.Service.Telemetry.Models.JsonEvent> ToEventsList<T>(System.Collections.Generic.IList<T> builderEvents);
    internal static PDX.SDK.Contracts.Service.Telemetry.Models.JsonEvent ToJsonEvent(PDX.SDK.Contracts.Service.Telemetry.Models.JsonEventBuilder builderEvent);
    internal static System.Collections.Generic.List<PDX.SDK.Contracts.Service.Telemetry.Models.JsonEvent> ToJsonEventsList(System.Collections.Generic.List<PDX.SDK.Contracts.Service.Telemetry.Models.JsonEventBuilder> builderEvents);
    internal static System.Collections.Generic.List<PDX.SDK.Contracts.Service.Telemetry.Models.JsonEvent> TransformV2EventsToV3Format<T>(System.Collections.Generic.IList<T> v2Events);
}
```


## Methods

- `internal static ToEventsList<T>(System.Collections.Generic.IList<T> builderEvents) : System.Collections.Generic.List<PDX.SDK.Contracts.Service.Telemetry.Models.JsonEvent>`  

```csharp
internal static System.Collections.Generic.List<PDX.SDK.Contracts.Service.Telemetry.Models.JsonEvent> ToEventsList<T>(System.Collections.Generic.IList<T> builderEvents);
```

- `internal static ToJsonEvent(PDX.SDK.Contracts.Service.Telemetry.Models.JsonEventBuilder builderEvent) : PDX.SDK.Contracts.Service.Telemetry.Models.JsonEvent`  

```csharp
internal static PDX.SDK.Contracts.Service.Telemetry.Models.JsonEvent ToJsonEvent(PDX.SDK.Contracts.Service.Telemetry.Models.JsonEventBuilder builderEvent);
```

- `internal static ToJsonEventsList(System.Collections.Generic.List<PDX.SDK.Contracts.Service.Telemetry.Models.JsonEventBuilder> builderEvents) : System.Collections.Generic.List<PDX.SDK.Contracts.Service.Telemetry.Models.JsonEvent>`  

```csharp
internal static System.Collections.Generic.List<PDX.SDK.Contracts.Service.Telemetry.Models.JsonEvent> ToJsonEventsList(System.Collections.Generic.List<PDX.SDK.Contracts.Service.Telemetry.Models.JsonEventBuilder> builderEvents);
```

- `internal static TransformV2EventsToV3Format<T>(System.Collections.Generic.IList<T> v2Events) : System.Collections.Generic.List<PDX.SDK.Contracts.Service.Telemetry.Models.JsonEvent>`  

```csharp
internal static System.Collections.Generic.List<PDX.SDK.Contracts.Service.Telemetry.Models.JsonEvent> TransformV2EventsToV3Format<T>(System.Collections.Generic.IList<T> v2Events);
```


