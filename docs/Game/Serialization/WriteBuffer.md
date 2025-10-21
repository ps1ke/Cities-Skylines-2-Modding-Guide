# Game.Serialization.WriteBuffer

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.Serialization.Entities.IWriteBuffer`, `System.IDisposable`  

## Code

```csharp
public class WriteBuffer : Colossal.Serialization.Entities.IWriteBuffer, System.IDisposable
{
    private Unity.Collections.NativeList<System.Byte> <buffer>k__BackingField;
    private Unity.Jobs.JobHandle m_WriteDependencies;
    private System.Boolean m_HasDependencies;
    private System.Boolean m_IsDone;

    public Unity.Collections.NativeList<System.Byte> buffer { get; private set; }
    public System.Boolean isCompleted { get; }

    public WriteBuffer();

    public System.Void CompleteDependencies();
    public System.Void Dispose();
    private System.Void DisposeBuffers();
    public System.Void Done(Unity.Jobs.JobHandle handle);
    public System.Void Done();
}
```


## Fields

- `private Unity.Collections.NativeList<System.Byte> <buffer>k__BackingField`  

```csharp
private Unity.Collections.NativeList<System.Byte> <buffer>k__BackingField;
```

- `private Unity.Jobs.JobHandle m_WriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_WriteDependencies;
```

- `private System.Boolean m_HasDependencies`  

```csharp
private System.Boolean m_HasDependencies;
```

- `private System.Boolean m_IsDone`  

```csharp
private System.Boolean m_IsDone;
```


## Properties

- `public Unity.Collections.NativeList<System.Byte> buffer { get; private set }`  

```csharp
public Unity.Collections.NativeList<System.Byte> buffer { get; private set; }
```

- `public System.Boolean isCompleted { get }`  

```csharp
public System.Boolean isCompleted { get; }
```


## Constructors

- `public WriteBuffer()`  

```csharp
public WriteBuffer();
```


## Methods

- `public CompleteDependencies() : System.Void`  

```csharp
public System.Void CompleteDependencies();
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `private DisposeBuffers() : System.Void`  

```csharp
private System.Void DisposeBuffers();
```

- `public Done(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public System.Void Done(Unity.Jobs.JobHandle handle);
```

- `public Done() : System.Void`  

```csharp
public System.Void Done();
```


