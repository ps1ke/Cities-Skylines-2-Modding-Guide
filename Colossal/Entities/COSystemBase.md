# Colossal.Entities.COSystemBase

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Entities`  

**Type:** class abstract public  

**Base:** `Unity.Entities.SystemBase`  

## Code

```csharp
public abstract class COSystemBase : Unity.Entities.SystemBase
{
    protected static Colossal.Logging.ILog baseLog;

    protected COSystemBase();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnStartRunning();
    protected virtual System.Void OnStopRunning();
}
```


## Fields

- `protected static Colossal.Logging.ILog baseLog`  

```csharp
protected static Colossal.Logging.ILog baseLog;
```


## Constructors

- `protected COSystemBase()`  

```csharp
protected COSystemBase();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
protected virtual System.Void OnStartRunning();
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
protected virtual System.Void OnStopRunning();
```


