# Game.SceneFlow.AsyncHelpers

**Assembly:** `Game`  
**Namespace:** `Game.SceneFlow`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class AsyncHelpers
{
    public static System.Threading.Tasks.Task<System.Boolean> AwaitWithTimeout(System.Threading.Tasks.Task task, System.TimeSpan timeout);
}
```


## Methods

- `public static AwaitWithTimeout(System.Threading.Tasks.Task task, System.TimeSpan timeout) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public static async Task<bool> AwaitWithTimeout(this Task task, TimeSpan timeout)
	{
		Task task2 = Task.Delay(timeout);
		return await Task.WhenAny(task, task2) == task;
	}
```


## Nested types

- `Game.SceneFlow.AsyncHelpers+<AwaitWithTimeout>d__0`  

