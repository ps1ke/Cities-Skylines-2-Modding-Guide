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
public static UnityWebRequestAwaiter ConfigureAwait(this UnityWebRequestAsyncOperation asyncOperation, Func<UnityWebRequestAsyncOperation, bool> updaterMethod, CancellationToken token, float connectionTimeout = 0f)
	{
		float progress = 0f;
		float time = Time.realtimeSinceStartup;
		GameManager.instance.RegisterUpdater(delegate
		{
			if (token.IsCancellationRequested)
			{
				asyncOperation.webRequest.Abort();
				return true;
			}
			if (connectionTimeout > 0f)
			{
				if (asyncOperation.progress > progress)
				{
					progress = asyncOperation.progress;
					time = Time.realtimeSinceStartup;
				}
				else if (Time.realtimeSinceStartup - time > connectionTimeout)
				{
					asyncOperation.webRequest.Abort();
					return true;
				}
			}
			return updaterMethod(asyncOperation);
		});
		return new UnityWebRequestAwaiter(asyncOperation);
	}
```

- `public static GetAwaiter(UnityEngine.Networking.UnityWebRequestAsyncOperation asyncOp) : Game.UnityWebRequestExtensionMethods+UnityWebRequestAwaiter`  

```csharp
public static UnityWebRequestAwaiter GetAwaiter(this UnityWebRequestAsyncOperation asyncOp)
	{
		return new UnityWebRequestAwaiter(asyncOp);
	}
```


## Nested types

- `Game.UnityWebRequestExtensionMethods+UnityWebRequestAwaiter`  
- `Game.UnityWebRequestExtensionMethods+<>c__DisplayClass1_0`  

