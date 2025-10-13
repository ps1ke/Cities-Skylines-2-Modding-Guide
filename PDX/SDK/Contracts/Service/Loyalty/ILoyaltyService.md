# PDX.SDK.Contracts.Service.Loyalty.ILoyaltyService

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Loyalty`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface ILoyaltyService
{
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Loyalty.Result.UserPointsResult> GetPoints(System.String pointType);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Loyalty.Result.LoyaltyStatusResult> GetStatus(System.String event, System.String type);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> RegisterEvent(System.String event, System.String type);
}
```


## Methods

- `public abstract GetPoints(System.String pointType = null) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Loyalty.Result.UserPointsResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Loyalty.Result.UserPointsResult> GetPoints(System.String pointType);
```

- `public abstract GetStatus(System.String event = null, System.String type = null) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Loyalty.Result.LoyaltyStatusResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Loyalty.Result.LoyaltyStatusResult> GetStatus(System.String event, System.String type);
```

- `public abstract RegisterEvent(System.String event, System.String type) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> RegisterEvent(System.String event, System.String type);
```


