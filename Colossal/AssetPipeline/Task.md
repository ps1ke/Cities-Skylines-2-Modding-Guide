# Colossal.AssetPipeline.MainThreadDispatcher+Task

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline`  

**Type:** class abstract public  

**Base:** `System.Object`  

## Code

```csharp
public abstract class Task
{
    protected System.Threading.AutoResetEvent m_ReadyEvent;

    protected Task();

    public abstract System.Void Execute();
    public System.Void Wait();
}
```


## Fields

- `protected System.Threading.AutoResetEvent m_ReadyEvent`  

```csharp
protected System.Threading.AutoResetEvent m_ReadyEvent;
```


## Constructors

- `protected Task()`  

```csharp
protected Task();
```


## Methods

- `public abstract Execute() : System.Void`  

```csharp
public abstract System.Void Execute();
```

- `public Wait() : System.Void`  

```csharp
public System.Void Wait();
```


## Nested types

- `Colossal.AssetPipeline.MainThreadDispatcher+Task+Void`  

