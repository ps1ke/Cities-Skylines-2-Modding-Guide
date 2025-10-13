# PDX.SDK.Contracts.Service.Telemetry.JsonBuilder

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Telemetry`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `PDX.SDK.Contracts.Service.Telemetry.IBuilder<PDX.SDK.Contracts.Service.Telemetry.Models.JsonEventBuilder>`  

## Code

```csharp
public class JsonBuilder : PDX.SDK.Contracts.Service.Telemetry.IBuilder<PDX.SDK.Contracts.Service.Telemetry.Models.JsonEventBuilder>
{
    public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Telemetry.Models.JsonEventBuilder> Events;

    public JsonBuilder();

    public PDX.SDK.Contracts.Service.Telemetry.Models.JsonEventBuilder AddEvent(System.String name);
    public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Telemetry.Models.JsonEventBuilder> Build();
}
```


## Fields

- `public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Telemetry.Models.JsonEventBuilder> Events`  

```csharp
public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Telemetry.Models.JsonEventBuilder> Events;
```


## Constructors

- `public JsonBuilder()`  

```csharp
public JsonBuilder();
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


