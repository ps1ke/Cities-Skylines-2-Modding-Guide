# PDX.SDK.Internal.Util.SynchronizationContextExtensions

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Internal.Util`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class SynchronizationContextExtensions
{
    public static System.Threading.Tasks.Task<T> OnMainThread<T>(System.Threading.SynchronizationContext unityMainThreadSynchronizationContext, System.Func<System.Threading.Tasks.Task<T>> func);
    public static System.Threading.Tasks.Task OnMainThread(System.Threading.SynchronizationContext unityMainThreadSynchronizationContext, System.Action action);
}
```


## Methods

- `public static OnMainThread<T>(System.Threading.SynchronizationContext unityMainThreadSynchronizationContext, System.Func<System.Threading.Tasks.Task<T>> func) : System.Threading.Tasks.Task<T>`  

```csharp
public static System.Threading.Tasks.Task<T> OnMainThread<T>(System.Threading.SynchronizationContext unityMainThreadSynchronizationContext, System.Func<System.Threading.Tasks.Task<T>> func);
```

- `public static OnMainThread(System.Threading.SynchronizationContext unityMainThreadSynchronizationContext, System.Action action) : System.Threading.Tasks.Task`  

```csharp
public static System.Threading.Tasks.Task OnMainThread(System.Threading.SynchronizationContext unityMainThreadSynchronizationContext, System.Action action);
```


## Nested types

- `PDX.SDK.Internal.Util.SynchronizationContextExtensions+<>c__DisplayClass0_0<T>`  
- `PDX.SDK.Internal.Util.SynchronizationContextExtensions+<>c__DisplayClass1_0`  

