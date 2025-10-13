# Colossal.Serialization.Entities.IWriteBuffer

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Serialization.Entities`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IWriteBuffer
{
    public Unity.Collections.NativeList<System.Byte> buffer { get; }

    public abstract System.Void Done(Unity.Jobs.JobHandle handle);
    public abstract System.Void Done();
}
```


## Properties

- `public Unity.Collections.NativeList<System.Byte> buffer { get }`  

```csharp
public Unity.Collections.NativeList<System.Byte> buffer { get; }
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


