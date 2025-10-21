# Game.Threading.UnityTask

**Assembly:** `Colossal.Core`  
**Namespace:** `Game.Threading`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class UnityTask
{
    public static System.Threading.Tasks.Task WaitForCPUFrame(System.Int32 count);
    public static System.Threading.Tasks.Task WaitForGPUFrame();
    private static System.Collections.IEnumerator WaitFrameCoroutine(System.Threading.Tasks.TaskCompletionSource<System.Boolean> tcs, System.Int32 count);
}
```


## Methods

- `public static WaitForCPUFrame(System.Int32 count) : System.Threading.Tasks.Task`  

```csharp
public static System.Threading.Tasks.Task WaitForCPUFrame(System.Int32 count);
```

- `public static WaitForGPUFrame() : System.Threading.Tasks.Task`  

```csharp
public static System.Threading.Tasks.Task WaitForGPUFrame();
```

- `private static WaitFrameCoroutine(System.Threading.Tasks.TaskCompletionSource<System.Boolean> tcs, System.Int32 count) : System.Collections.IEnumerator`  

```csharp
private static System.Collections.IEnumerator WaitFrameCoroutine(System.Threading.Tasks.TaskCompletionSource<System.Boolean> tcs, System.Int32 count);
```


## Nested types

- `Game.Threading.UnityTask+<>c__DisplayClass2_0`  
- `Game.Threading.UnityTask+<WaitForGPUFrame>d__2`  
- `Game.Threading.UnityTask+<WaitFrameCoroutine>d__1`  

