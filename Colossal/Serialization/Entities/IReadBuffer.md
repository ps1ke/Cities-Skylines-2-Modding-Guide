# Colossal.Serialization.Entities.IReadBuffer

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Serialization.Entities`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IReadBuffer
{
    public Unity.Collections.NativeArray<System.Byte> buffer { get; }
    public Unity.Collections.NativeReference<System.Int32> position { get; }

    public abstract System.Void Done(Unity.Jobs.JobHandle handle);
    public abstract System.Void Done();
}
```


## Properties

- `public Unity.Collections.NativeArray<System.Byte> buffer { get }`  

```csharp
public Unity.Collections.NativeArray<System.Byte> buffer { get; }
```

- `public Unity.Collections.NativeReference<System.Int32> position { get }`  

```csharp
public Unity.Collections.NativeReference<System.Int32> position { get; }
```


## Methods

- `public abstract Done(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public abstract System.Void Done(Unity.Jobs.JobHandle handle);
```

- `public abstract Done() : System.Void`  

```csharp
public abstract System.Void Done();
```


