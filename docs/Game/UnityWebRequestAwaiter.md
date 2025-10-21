# Game.UnityWebRequestExtensionMethods+UnityWebRequestAwaiter

**Assembly:** `Game`  
**Namespace:** `Game`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.Runtime.CompilerServices.INotifyCompletion`  

## Code

```csharp
public class UnityWebRequestAwaiter : System.Runtime.CompilerServices.INotifyCompletion
{
    private UnityEngine.Networking.UnityWebRequestAsyncOperation asyncOp;
    private System.Action continuation;

    public System.Boolean IsCompleted { get; }

    public UnityWebRequestAwaiter(UnityEngine.Networking.UnityWebRequestAsyncOperation asyncOp);

    public Game.UnityWebRequestExtensionMethods+UnityWebRequestAwaiter GetAwaiter();
    public UnityEngine.Networking.UnityWebRequest+Result GetResult();
    public System.Void OnCompleted(System.Action continuation);
    public System.Void OnRequestCompleted(UnityEngine.AsyncOperation obj);
}
```


## Fields

- `private UnityEngine.Networking.UnityWebRequestAsyncOperation asyncOp`  

```csharp
private UnityEngine.Networking.UnityWebRequestAsyncOperation asyncOp;
```

- `private System.Action continuation`  

```csharp
private System.Action continuation;
```


## Properties

- `public System.Boolean IsCompleted { get }`  

```csharp
public System.Boolean IsCompleted { get; }
```


## Constructors

- `public UnityWebRequestAwaiter(UnityEngine.Networking.UnityWebRequestAsyncOperation asyncOp)`  

```csharp
public UnityWebRequestAwaiter(UnityEngine.Networking.UnityWebRequestAsyncOperation asyncOp);
```


## Methods

- `public GetAwaiter() : Game.UnityWebRequestExtensionMethods+UnityWebRequestAwaiter`  

```csharp
public Game.UnityWebRequestExtensionMethods+UnityWebRequestAwaiter GetAwaiter();
```

- `public GetResult() : UnityEngine.Networking.UnityWebRequest+Result`  

```csharp
public UnityEngine.Networking.UnityWebRequest+Result GetResult();
```

- `public OnCompleted(System.Action continuation) : System.Void`  

```csharp
public System.Void OnCompleted(System.Action continuation);
```

- `public OnRequestCompleted(UnityEngine.AsyncOperation obj) : System.Void`  

```csharp
public System.Void OnRequestCompleted(UnityEngine.AsyncOperation obj);
```


