# Game.UnityWebRequestExtensionMethods

**Assembly:** `Game`  
**Namespace:** `Game`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class UnityWebRequestExtensionMethods
{
    public static Game.UnityWebRequestExtensionMethods+UnityWebRequestAwaiter ConfigureAwait(UnityEngine.Networking.UnityWebRequestAsyncOperation asyncOperation, System.Func<UnityEngine.Networking.UnityWebRequestAsyncOperation, System.Boolean> updaterMethod, System.Threading.CancellationToken token, System.Single connectionTimeout);
    public static Game.UnityWebRequestExtensionMethods+UnityWebRequestAwaiter GetAwaiter(UnityEngine.Networking.UnityWebRequestAsyncOperation asyncOp);
}
```


## Methods

- `public static ConfigureAwait(UnityEngine.Networking.UnityWebRequestAsyncOperation asyncOperation, System.Func<UnityEngine.Networking.UnityWebRequestAsyncOperation, System.Boolean> updaterMethod, System.Threading.CancellationToken token, System.Single connectionTimeout = 0) : Game.UnityWebRequestExtensionMethods+UnityWebRequestAwaiter`  

```csharp
public static Game.UnityWebRequestExtensionMethods+UnityWebRequestAwaiter ConfigureAwait(UnityEngine.Networking.UnityWebRequestAsyncOperation asyncOperation, System.Func<UnityEngine.Networking.UnityWebRequestAsyncOperation, System.Boolean> updaterMethod, System.Threading.CancellationToken token, System.Single connectionTimeout);
```

- `public static GetAwaiter(UnityEngine.Networking.UnityWebRequestAsyncOperation asyncOp) : Game.UnityWebRequestExtensionMethods+UnityWebRequestAwaiter`  

```csharp
public static Game.UnityWebRequestExtensionMethods+UnityWebRequestAwaiter GetAwaiter(UnityEngine.Networking.UnityWebRequestAsyncOperation asyncOp);
```


## Nested types

- `Game.UnityWebRequestExtensionMethods+UnityWebRequestAwaiter`  
- `Game.UnityWebRequestExtensionMethods+<>c__DisplayClass1_0`  

