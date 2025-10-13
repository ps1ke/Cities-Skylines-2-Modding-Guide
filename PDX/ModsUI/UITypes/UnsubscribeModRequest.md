# PDX.ModsUI.UITypes.UnsubscribeModRequest

**Assembly:** `PDX.ModsUI`  
**Namespace:** `PDX.ModsUI.UITypes`  

**Type:** class public  

**Base:** `PDX.ModsUI.UITypes.Request`  

**Attributes:** `CoherentType`  

## Code

```csharp
public class UnsubscribeModRequest : PDX.ModsUI.UITypes.Request
{
    public System.Int32 ModId;
    public System.Int32 PlaysetId;
    public PDX.ModsUI.UITypes.SubscriptionTelemetry Telemetry;

    public UnsubscribeModRequest();

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

- `public PDX.ModsUI.UITypes.SubscriptionTelemetry Telemetry`  

```csharp
public PDX.ModsUI.UITypes.SubscriptionTelemetry Telemetry;
```


## Constructors

- `public UnsubscribeModRequest()`  

```csharp
public UnsubscribeModRequest();
```


