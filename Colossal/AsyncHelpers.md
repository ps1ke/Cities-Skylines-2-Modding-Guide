# Colossal.AsyncHelpers

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class AsyncHelpers
{
    public static System.Void RunSync(System.Func<System.Threading.Tasks.Task> task);
    public static T RunSync<T>(System.Func<System.Threading.Tasks.Task<T>> task);
}
```


## Methods

- `public static RunSync(System.Func<System.Threading.Tasks.Task> task) : System.Void`  

```csharp
public static System.Void RunSync(System.Func<System.Threading.Tasks.Task> task);
```

- `public static RunSync<T>(System.Func<System.Threading.Tasks.Task<T>> task) : T`  

```csharp
public static T RunSync<T>(System.Func<System.Threading.Tasks.Task<T>> task);
```


## Nested types

- `Colossal.AsyncHelpers+ExclusiveSynchronizationContext`  
- `Colossal.AsyncHelpers+<>c__DisplayClass0_0`  
- `Colossal.AsyncHelpers+<>c__DisplayClass1_0<T>`  

