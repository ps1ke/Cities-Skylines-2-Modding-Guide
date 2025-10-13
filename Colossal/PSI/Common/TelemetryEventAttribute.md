# Colossal.PSI.Common.TelemetryEventAttribute

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** class public  

**Base:** `System.Attribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class TelemetryEventAttribute : System.Attribute
{
    private readonly System.String <eventName>k__BackingField;
    private readonly System.Type <payloadType>k__BackingField;

    public System.String eventName { get; }
    public System.Type payloadType { get; }

    public TelemetryEventAttribute(System.String eventName, System.Type payloadType);

}
```


## Fields

- `private readonly System.String <eventName>k__BackingField`  

```csharp
private readonly System.String <eventName>k__BackingField;
```

- `private readonly System.Type <payloadType>k__BackingField`  

```csharp
private readonly System.Type <payloadType>k__BackingField;
```


## Properties

- `public System.String eventName { get }`  

```csharp
public System.String eventName { get; }
```

- `public System.Type payloadType { get }`  

```csharp
public System.Type payloadType { get; }
```


## Constructors

- `public TelemetryEventAttribute(System.String eventName, System.Type payloadType)`  

```csharp
public TelemetryEventAttribute(System.String eventName, System.Type payloadType);
```


