# Game.UnityWebRequestExtensionMethods

**Assembly:**  
Assembly-CSharp (game/mod assembly)

**Namespace:** 
Game

**Type:**
static class

**Base:**
System.Object

**Summary:** 
Extension methods and an awaiter implementation for UnityWebRequestAsyncOperation that make UnityWebRequest awaitable with C# async/await. Also provides a ConfigureAwait-like helper that integrates request cancellation, optional connection-timeout handling, and a custom updater callback tied into the game's GameManager update loop.

---

## Fields

- `private UnityWebRequestAsyncOperation asyncOp` (inside UnityWebRequestAwaiter)  
Holds the UnityWebRequestAsyncOperation instance the awaiter is wrapping. Used to observe completion and fetch the final result.

- `private Action continuation` (inside UnityWebRequestAwaiter)  
Stores the continuation/delegate to invoke when the request completes so that awaiting code can resume.

## Properties

- `public bool IsCompleted { get; }` (inside UnityWebRequestAwaiter)  
Read-only property indicating whether the wrapped UnityWebRequestAsyncOperation has finished (returns asyncOp.isDone). Used by the C# await machinery to decide whether to schedule a continuation.

## Constructors

- `public UnityWebRequestAwaiter(UnityWebRequestAsyncOperation asyncOp)`  
Initializes the awaiter and registers a callback on asyncOp.completed to be notified when the operation finishes. Sets up internal asyncOp reference.

## Methods

- `public UnityWebRequest.Result GetResult()` (inside UnityWebRequestAwaiter)  
Returns the UnityWebRequest.Result from the underlying web request (asyncOp.webRequest.result). Called by the await infrastructure to obtain the operation result.

- `public void OnCompleted(Action continuation)` (inside UnityWebRequestAwaiter)  
Called by the compiler-generated await code to provide a continuation callback. Stores the continuation and, if the operation is already complete, invokes the completion handler immediately.

- `public void OnRequestCompleted(AsyncOperation obj)` (inside UnityWebRequestAwaiter)  
Internal completion handler attached to asyncOp.completed; invokes the stored continuation if present.

- `public UnityWebRequestAwaiter GetAwaiter()` (inside UnityWebRequestAwaiter)  
Returns this awaiter instance so that the async/await pattern works directly on the awaiter object.

- `public static UnityWebRequestAwaiter GetAwaiter(this UnityWebRequestAsyncOperation asyncOp)` (extension method)  
Convenience extension allowing code to directly await a UnityWebRequestAsyncOperation: `await request.SendWebRequest()`.

- `public static UnityWebRequestAwaiter ConfigureAwait(this UnityWebRequestAsyncOperation asyncOperation, Func<UnityWebRequestAsyncOperation, bool> updaterMethod, CancellationToken token, float connectionTimeout = 0f)` (extension method)  
Registers a per-frame updater with GameManager.instance.RegisterUpdater that:
  - aborts the web request if the provided CancellationToken is cancelled,
  - enforces a connection timeout (if connectionTimeout > 0) by checking progress stagnation,
  - invokes the provided updaterMethod each frame to determine whether to continue updating.
Returns an awaiter for the operation so callers can still await the asyncOperation while the updater monitors and controls it.

Example usage scenarios:
  - Awaiting UnityWebRequest operations in async methods.
  - Adding cancellation and connection-timeout logic integrated with the game's frame updater loop.

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

Notes and caveats:
- The awaiter wraps UnityWebRequestAsyncOperation and depends on Unity's AsyncOperation.completed callback; continuations will run on the thread/context that Unity invokes those callbacks on (normally the main thread).
- ConfigureAwait uses GameManager.instance.RegisterUpdater to run per-frame checks; ensure GameManager is available and that RegisterUpdater semantics match expectations (updater delegate should return true to unregister).
- Aborting a UnityWebRequest sets its result to indicate failure; callers should inspect GetResult (and UnityWebRequest.error / response code as needed) after awaiting to handle errors.