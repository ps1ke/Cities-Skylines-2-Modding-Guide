# Colossal.AsyncUtils

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  

## Code

```csharp
public class AsyncUtils : UnityEngine.MonoBehaviour
{
    public AsyncUtils();

    public static System.Threading.Tasks.Task CopyFileAsync(System.String sourceFile, System.String destinationFile, System.Boolean overwrite);
    public static System.Threading.Tasks.Task CopyFileAsync(System.String sourceFile, System.String destinationFile, System.Boolean overwrite, System.Threading.CancellationToken cancellationToken);
    public static System.Threading.Tasks.Task DeleteDirectoryAsync(System.String directoryPath, System.Boolean recursive, System.Int32 checkIntervalMs, System.Int32 timeoutMs);
    public static System.Threading.Tasks.Task DeleteDirectoryAsync(System.String directoryPath, System.Boolean recursive, System.Threading.CancellationToken cancellationToken, System.Int32 checkIntervalMs, System.Int32 timeoutMs);
    public static System.Threading.Tasks.Task DeleteFileAsync(System.String filePath, System.Int32 checkIntervalMs, System.Int32 timeoutMs);
    public static System.Threading.Tasks.Task DeleteFileAsync(System.String filePath, System.Threading.CancellationToken cancellationToken, System.Int32 checkIntervalMs, System.Int32 timeoutMs);
    public static System.Threading.Tasks.Task WaitForAction(System.Func<System.Boolean> func, System.Int32 delayMs);
    public static System.Threading.Tasks.Task WaitForAction(System.Func<System.Boolean> func, System.Threading.CancellationToken token, System.Int32 delayMs);
}
```


## Constructors

- `public AsyncUtils()`  

```csharp
public AsyncUtils();
```


## Methods

- `public static CopyFileAsync(System.String sourceFile, System.String destinationFile, System.Boolean overwrite) : System.Threading.Tasks.Task`  

```csharp
public static System.Threading.Tasks.Task CopyFileAsync(System.String sourceFile, System.String destinationFile, System.Boolean overwrite);
```

- `public static CopyFileAsync(System.String sourceFile, System.String destinationFile, System.Boolean overwrite, System.Threading.CancellationToken cancellationToken) : System.Threading.Tasks.Task`  

```csharp
public static System.Threading.Tasks.Task CopyFileAsync(System.String sourceFile, System.String destinationFile, System.Boolean overwrite, System.Threading.CancellationToken cancellationToken);
```

- `public static DeleteDirectoryAsync(System.String directoryPath, System.Boolean recursive, System.Int32 checkIntervalMs = 100, System.Int32 timeoutMs = 5000) : System.Threading.Tasks.Task`  

```csharp
public static System.Threading.Tasks.Task DeleteDirectoryAsync(System.String directoryPath, System.Boolean recursive, System.Int32 checkIntervalMs, System.Int32 timeoutMs);
```

- `public static DeleteDirectoryAsync(System.String directoryPath, System.Boolean recursive, System.Threading.CancellationToken cancellationToken, System.Int32 checkIntervalMs = 100, System.Int32 timeoutMs = 5000) : System.Threading.Tasks.Task`  

```csharp
public static System.Threading.Tasks.Task DeleteDirectoryAsync(System.String directoryPath, System.Boolean recursive, System.Threading.CancellationToken cancellationToken, System.Int32 checkIntervalMs, System.Int32 timeoutMs);
```

- `public static DeleteFileAsync(System.String filePath, System.Int32 checkIntervalMs = 100, System.Int32 timeoutMs = 5000) : System.Threading.Tasks.Task`  

```csharp
public static System.Threading.Tasks.Task DeleteFileAsync(System.String filePath, System.Int32 checkIntervalMs, System.Int32 timeoutMs);
```

- `public static DeleteFileAsync(System.String filePath, System.Threading.CancellationToken cancellationToken, System.Int32 checkIntervalMs = 100, System.Int32 timeoutMs = 5000) : System.Threading.Tasks.Task`  

```csharp
public static System.Threading.Tasks.Task DeleteFileAsync(System.String filePath, System.Threading.CancellationToken cancellationToken, System.Int32 checkIntervalMs, System.Int32 timeoutMs);
```

- `public static WaitForAction(System.Func<System.Boolean> func, System.Int32 delayMs = 100) : System.Threading.Tasks.Task`  

```csharp
public static System.Threading.Tasks.Task WaitForAction(System.Func<System.Boolean> func, System.Int32 delayMs);
```

- `public static WaitForAction(System.Func<System.Boolean> func, System.Threading.CancellationToken token, System.Int32 delayMs = 100) : System.Threading.Tasks.Task`  

```csharp
public static System.Threading.Tasks.Task WaitForAction(System.Func<System.Boolean> func, System.Threading.CancellationToken token, System.Int32 delayMs);
```


## Nested types

- `Colossal.AsyncUtils+<>c__DisplayClass5_0`  
- `Colossal.AsyncUtils+<>c__DisplayClass7_0`  
- `Colossal.AsyncUtils+<CopyFileAsync>d__3`  
- `Colossal.AsyncUtils+<DeleteDirectoryAsync>d__7`  
- `Colossal.AsyncUtils+<DeleteFileAsync>d__5`  
- `Colossal.AsyncUtils+<WaitForAction>d__1`  

