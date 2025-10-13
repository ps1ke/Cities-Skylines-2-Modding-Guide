# PDX.SDK.Contracts.Service.Telemetry.Models.JsonEventBuilder

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Telemetry.Models`  

**Type:** class public  

**Base:** `PDX.SDK.Contracts.Service.Telemetry.Models.JsonEvent`  
**Implements:** `PDX.SDK.Contracts.Service.Telemetry.Models.IEvent`, `PDX.SDK.Contracts.Service.Telemetry.IBuilder<PDX.SDK.Contracts.Service.Telemetry.Models.JsonEventBuilder>`  

## Code

```csharp
public class JsonEventBuilder : PDX.SDK.Contracts.Service.Telemetry.Models.JsonEvent, PDX.SDK.Contracts.Service.Telemetry.Models.IEvent, PDX.SDK.Contracts.Service.Telemetry.IBuilder<PDX.SDK.Contracts.Service.Telemetry.Models.JsonEventBuilder>
{
    private PDX.SDK.Contracts.Service.Telemetry.JsonBuilder Parent;

    public JsonEventBuilder(System.String name, PDX.SDK.Contracts.Service.Telemetry.JsonBuilder parent);
    public JsonEventBuilder(System.String name, System.Object payload, PDX.SDK.Contracts.Service.Telemetry.JsonBuilder parent);
    public JsonEventBuilder(System.String name, System.Object payload, System.String schemaVersion, PDX.SDK.Contracts.Service.Telemetry.JsonBuilder parent);

    public PDX.SDK.Contracts.Service.Telemetry.Models.JsonEventBuilder AddEvent(System.String name);
    public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Telemetry.Models.JsonEventBuilder> Build();
    public PDX.SDK.Contracts.Service.Telemetry.Models.JsonEventBuilder SetPayload(System.Object payload);
    public PDX.SDK.Contracts.Service.Telemetry.Models.JsonEventBuilder SetSchemaVersion(System.String schemaVersion);
}
```


## Fields

- `private PDX.SDK.Contracts.Service.Telemetry.JsonBuilder Parent`  

```csharp
private PDX.SDK.Contracts.Service.Telemetry.JsonBuilder Parent;
```


## Constructors

- `public JsonEventBuilder(System.String name, PDX.SDK.Contracts.Service.Telemetry.JsonBuilder parent)`  

```csharp
public JsonEventBuilder(System.String name, PDX.SDK.Contracts.Service.Telemetry.JsonBuilder parent);
```

- `public JsonEventBuilder(System.String name, System.Object payload, PDX.SDK.Contracts.Service.Telemetry.JsonBuilder parent)`  

```csharp
public JsonEventBuilder(System.String name, System.Object payload, PDX.SDK.Contracts.Service.Telemetry.JsonBuilder parent);
```

- `public JsonEventBuilder(System.String name, System.Object payload, System.String schemaVersion, PDX.SDK.Contracts.Service.Telemetry.JsonBuilder parent)`  

```csharp
public JsonEventBuilder(System.String name, System.Object payload, System.String schemaVersion, PDX.SDK.Contracts.Service.Telemetry.JsonBuilder parent);
```


## Methods

- `public AddEvent(System.String name) : PDX.SDK.Contracts.Service.Telemetry.Models.JsonEventBuilder`  

```csharp
public PDX.SDK.Contracts.Service.Telemetry.Models.JsonEventBuilder AddEvent(System.String name);
```

- `public Build() : System.Collections.Generic.List<PDX.SDK.Contracts.Service.Telemetry.Models.JsonEventBuilder>`  

```csharp
public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Telemetry.Models.JsonEventBuilder> Build();
```

- `public SetPayload(System.Object payload) : PDX.SDK.Contracts.Service.Telemetry.Models.JsonEventBuilder`  

```csharp
public PDX.SDK.Contracts.Service.Telemetry.Models.JsonEventBuilder SetPayload(System.Object payload);
```

- `public SetSchemaVersion(System.String schemaVersion) : PDX.SDK.Contracts.Service.Telemetry.Models.JsonEventBuilder`  

```csharp
public PDX.SDK.Contracts.Service.Telemetry.Models.JsonEventBuilder SetSchemaVersion(System.String schemaVersion);
```


