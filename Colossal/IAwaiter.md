# Colossal.IAwaiter

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** interface abstract public  

**Implements:** `System.Runtime.CompilerServices.INotifyCompletion`  

## Code

```csharp
public abstract interface IAwaiter : System.Runtime.CompilerServices.INotifyCompletion
{
    public System.Boolean IsCompleted { get; }

    public abstract System.Void GetResult();
}
```


## Properties

- `public System.Boolean IsCompleted { get }`  

```csharp
public System.Boolean IsCompleted { get; }
```


## Methods

- `public abstract GetResult() : System.Void`  

```csharp
public abstract System.Void GetResult();
```


