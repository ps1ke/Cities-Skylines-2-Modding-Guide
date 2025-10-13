# PDX.SDK.Contracts.Service.Telemetry.Models.KeyValueEventBuilder

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Telemetry.Models`  

**Type:** class public  

**Base:** `PDX.SDK.Contracts.Service.Telemetry.Models.KeyValueEvent`  
**Implements:** `PDX.SDK.Contracts.Service.Telemetry.Models.IEvent`, `PDX.SDK.Contracts.Service.Telemetry.IBuilder<PDX.SDK.Contracts.Service.Telemetry.Models.KeyValueEventBuilder>`  

## Code

```csharp
public class KeyValueEventBuilder : PDX.SDK.Contracts.Service.Telemetry.Models.KeyValueEvent, PDX.SDK.Contracts.Service.Telemetry.Models.IEvent, PDX.SDK.Contracts.Service.Telemetry.IBuilder<PDX.SDK.Contracts.Service.Telemetry.Models.KeyValueEventBuilder>
{
    private PDX.SDK.Contracts.Service.Telemetry.KeyValueBuilder Parent;

    public KeyValueEventBuilder(System.String name, PDX.SDK.Contracts.Service.Telemetry.KeyValueBuilder parent);

    public PDX.SDK.Contracts.Service.Telemetry.Models.KeyValueEventBuilder AddEvent(System.String name);
    public PDX.SDK.Contracts.Service.Telemetry.Models.KeyValueEventBuilder AddKeyValue(System.String key, System.String value);
    public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Telemetry.Models.KeyValueEventBuilder> Build();
}
```


## Fields

- `private PDX.SDK.Contracts.Service.Telemetry.KeyValueBuilder Parent`  

```csharp
private PDX.SDK.Contracts.Service.Telemetry.KeyValueBuilder Parent;
```


## Constructors

- `public KeyValueEventBuilder(System.String name, PDX.SDK.Contracts.Service.Telemetry.KeyValueBuilder parent)`  

```csharp
public KeyValueEventBuilder(System.String name, PDX.SDK.Contracts.Service.Telemetry.KeyValueBuilder parent);
```


## Methods

- `public AddEvent(System.String name) : PDX.SDK.Contracts.Service.Telemetry.Models.KeyValueEventBuilder`  

```csharp
public PDX.SDK.Contracts.Service.Telemetry.Models.KeyValueEventBuilder AddEvent(System.String name);
```

- `public AddKeyValue(System.String key, System.String value) : PDX.SDK.Contracts.Service.Telemetry.Models.KeyValueEventBuilder`  

```csharp
public PDX.SDK.Contracts.Service.Telemetry.Models.KeyValueEventBuilder AddKeyValue(System.String key, System.String value);
```

- `public Build() : System.Collections.Generic.List<PDX.SDK.Contracts.Service.Telemetry.Models.KeyValueEventBuilder>`  

```csharp
public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Telemetry.Models.KeyValueEventBuilder> Build();
```


