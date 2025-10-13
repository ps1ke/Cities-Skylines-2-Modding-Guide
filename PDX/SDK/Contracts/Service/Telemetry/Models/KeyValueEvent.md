# PDX.SDK.Contracts.Service.Telemetry.Models.KeyValueEvent

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Telemetry.Models`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `PDX.SDK.Contracts.Service.Telemetry.Models.IEvent`  

## Code

```csharp
public class KeyValueEvent : PDX.SDK.Contracts.Service.Telemetry.Models.IEvent
{
    private System.String <Name>k__BackingField;
    private System.Collections.Generic.IList<System.Collections.Generic.KeyValuePair<System.String, System.String>> <KeyValues>k__BackingField;

    public System.String Name { get; set; }
    public System.Collections.Generic.IList<System.Collections.Generic.KeyValuePair<System.String, System.String>> KeyValues { get; set; }

    public KeyValueEvent();

}
```


## Fields

- `private System.String <Name>k__BackingField`  

```csharp
private System.String <Name>k__BackingField;
```

- `private System.Collections.Generic.IList<System.Collections.Generic.KeyValuePair<System.String, System.String>> <KeyValues>k__BackingField`  

```csharp
private System.Collections.Generic.IList<System.Collections.Generic.KeyValuePair<System.String, System.String>> <KeyValues>k__BackingField;
```


## Properties

- `public System.String Name { get; set }`  

```csharp
public System.String Name { get; set; }
```

- `public System.Collections.Generic.IList<System.Collections.Generic.KeyValuePair<System.String, System.String>> KeyValues { get; set }`  

```csharp
public System.Collections.Generic.IList<System.Collections.Generic.KeyValuePair<System.String, System.String>> KeyValues { get; set; }
```


## Constructors

- `public KeyValueEvent()`  

```csharp
public KeyValueEvent();
```


