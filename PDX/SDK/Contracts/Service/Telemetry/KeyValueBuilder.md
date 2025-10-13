# PDX.SDK.Contracts.Service.Telemetry.KeyValueBuilder

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Telemetry`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `PDX.SDK.Contracts.Service.Telemetry.IBuilder<PDX.SDK.Contracts.Service.Telemetry.Models.KeyValueEventBuilder>`  

## Code

```csharp
public class KeyValueBuilder : PDX.SDK.Contracts.Service.Telemetry.IBuilder<PDX.SDK.Contracts.Service.Telemetry.Models.KeyValueEventBuilder>
{
    public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Telemetry.Models.KeyValueEventBuilder> Events;

    public KeyValueBuilder();

    public PDX.SDK.Contracts.Service.Telemetry.Models.KeyValueEventBuilder AddEvent(System.String name);
    public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Telemetry.Models.KeyValueEventBuilder> Build();
}
```


## Fields

- `public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Telemetry.Models.KeyValueEventBuilder> Events`  

```csharp
public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Telemetry.Models.KeyValueEventBuilder> Events;
```


## Constructors

- `public KeyValueBuilder()`  

```csharp
public KeyValueBuilder();
```


## Methods

- `public AddEvent(System.String name) : PDX.SDK.Contracts.Service.Telemetry.Models.KeyValueEventBuilder`  

```csharp
public PDX.SDK.Contracts.Service.Telemetry.Models.KeyValueEventBuilder AddEvent(System.String name);
```

- `public Build() : System.Collections.Generic.List<PDX.SDK.Contracts.Service.Telemetry.Models.KeyValueEventBuilder>`  

```csharp
public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Telemetry.Models.KeyValueEventBuilder> Build();
```


