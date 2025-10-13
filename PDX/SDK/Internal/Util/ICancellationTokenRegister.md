# PDX.SDK.Internal.Util.ICancellationTokenRegister

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Internal.Util`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface ICancellationTokenRegister
{
    public abstract System.Void CancelAllTokens(PDX.SDK.Contracts.Internal.FlowData flowData);
    public abstract System.Void CancelAllTokensOfType(PDX.SDK.Internal.Enums.CancellationTokenRegistrationType type, PDX.SDK.Contracts.Internal.FlowData flowData);
    public abstract System.Threading.CancellationToken GetToken(PDX.SDK.Internal.Enums.CancellationTokenRegistrationType type, PDX.SDK.Contracts.Internal.FlowData flowData);
    public abstract System.Void RemoveToken(System.Threading.CancellationToken token);
}
```


## Methods

- `public abstract CancelAllTokens(PDX.SDK.Contracts.Internal.FlowData flowData = null) : System.Void`  

```csharp
public abstract System.Void CancelAllTokens(PDX.SDK.Contracts.Internal.FlowData flowData);
```

- `public abstract CancelAllTokensOfType(PDX.SDK.Internal.Enums.CancellationTokenRegistrationType type, PDX.SDK.Contracts.Internal.FlowData flowData = null) : System.Void`  

```csharp
public abstract System.Void CancelAllTokensOfType(PDX.SDK.Internal.Enums.CancellationTokenRegistrationType type, PDX.SDK.Contracts.Internal.FlowData flowData);
```

- `public abstract GetToken(PDX.SDK.Internal.Enums.CancellationTokenRegistrationType type, PDX.SDK.Contracts.Internal.FlowData flowData = null) : System.Threading.CancellationToken`  

```csharp
public abstract System.Threading.CancellationToken GetToken(PDX.SDK.Internal.Enums.CancellationTokenRegistrationType type, PDX.SDK.Contracts.Internal.FlowData flowData);
```

- `public abstract RemoveToken(System.Threading.CancellationToken token) : System.Void`  

```csharp
public abstract System.Void RemoveToken(System.Threading.CancellationToken token);
```


