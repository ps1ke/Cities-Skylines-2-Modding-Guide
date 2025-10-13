# Colossal.IO.AssetDatabase.UnityWebRequestAwaiter

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.Runtime.CompilerServices.INotifyCompletion`  

## Code

```csharp
public class UnityWebRequestAwaiter : System.Runtime.CompilerServices.INotifyCompletion
{
    private UnityEngine.Networking.UnityWebRequestAsyncOperation asyncOp;
    private System.Action callback;

    public System.Boolean IsCompleted { get; }

    public UnityWebRequestAwaiter(UnityEngine.Networking.UnityWebRequestAsyncOperation asyncOp);

    public System.Void GetResult();
    public System.Void OnCompleted(System.Action callback);
    private System.Void OnRequestCompleted(UnityEngine.AsyncOperation obj);
}
```


## Fields

- `private UnityEngine.Networking.UnityWebRequestAsyncOperation asyncOp`  

```csharp
private UnityEngine.Networking.UnityWebRequestAsyncOperation asyncOp;
```

- `private System.Action callback`  

```csharp
private System.Action callback;
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

- `public GetResult() : System.Void`  

```csharp
public System.Void GetResult();
```

- `public OnCompleted(System.Action callback) : System.Void`  

```csharp
public System.Void OnCompleted(System.Action callback);
```

- `private OnRequestCompleted(UnityEngine.AsyncOperation obj) : System.Void`  

```csharp
private System.Void OnRequestCompleted(UnityEngine.AsyncOperation obj);
```


