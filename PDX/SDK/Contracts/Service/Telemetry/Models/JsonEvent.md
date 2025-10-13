# PDX.SDK.Contracts.Service.Telemetry.Models.JsonEvent

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Telemetry.Models`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `PDX.SDK.Contracts.Service.Telemetry.Models.IEvent`  

## Code

```csharp
public class JsonEvent : PDX.SDK.Contracts.Service.Telemetry.Models.IEvent
{
    private System.String <Name>k__BackingField;
    private System.Object <Payload>k__BackingField;
    private System.String <SchemaVersion>k__BackingField;

    public System.String Name { get; set; }
    public System.Object Payload { get; set; }
    public System.String SchemaVersion { get; set; }

    public JsonEvent();

}
```


## Fields

- `private System.String <Name>k__BackingField`  

```csharp
private System.String <Name>k__BackingField;
```

- `private System.Object <Payload>k__BackingField`  

```csharp
private System.Object <Payload>k__BackingField;
```

- `private System.String <SchemaVersion>k__BackingField`  

```csharp
private System.String <SchemaVersion>k__BackingField;
```


## Properties

- `public System.String Name { get; set }`  

```csharp
public System.String Name { get; set; }
```

- `public System.Object Payload { get; set }`  

```csharp
public System.Object Payload { get; set; }
```

- `public System.String SchemaVersion { get; set }`  

```csharp
public System.String SchemaVersion { get; set; }
```


## Constructors

- `public JsonEvent()`  

```csharp
public JsonEvent();
```


