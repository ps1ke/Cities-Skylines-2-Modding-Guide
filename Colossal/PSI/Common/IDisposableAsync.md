# Colossal.PSI.Common.IDisposableAsync

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IDisposableAsync
{
    public abstract System.Threading.Tasks.Task Dispose(System.Boolean disposeEvents, System.Threading.CancellationToken token);
}
```


## Methods

- `public abstract Dispose(System.Boolean disposeEvents, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public abstract System.Threading.Tasks.Task Dispose(System.Boolean disposeEvents, System.Threading.CancellationToken token);
```


