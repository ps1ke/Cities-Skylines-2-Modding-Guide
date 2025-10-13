# PDX.ModsUI.UITypes.SubscribeModRequest

**Assembly:** `PDX.ModsUI`  
**Namespace:** `PDX.ModsUI.UITypes`  

**Type:** class public  

**Base:** `PDX.ModsUI.UITypes.Request`  

**Attributes:** `CoherentType`  

## Code

```csharp
public class SubscribeModRequest : PDX.ModsUI.UITypes.Request
{
    public System.Int32 ModId;
    public System.Int32 PlaysetId;
    public System.String Version;
    public PDX.ModsUI.UITypes.SubscriptionTelemetry Telemetry;

    public SubscribeModRequest();

}
```


## Fields

- `public System.Int32 ModId`  

```csharp
public System.Int32 ModId;
```

- `public System.Int32 PlaysetId`  

```csharp
public System.Int32 PlaysetId;
```

- `public System.String Version`  

```csharp
public System.String Version;
```

- `public PDX.ModsUI.UITypes.SubscriptionTelemetry Telemetry`  

```csharp
public PDX.ModsUI.UITypes.SubscriptionTelemetry Telemetry;
```


## Constructors

- `public SubscribeModRequest()`  

```csharp
public SubscribeModRequest();
```


