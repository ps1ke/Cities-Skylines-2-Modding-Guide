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
public WriteBuffer()
	{
		buffer = new NativeList<byte>(Allocator.Persistent);
	}
```


## Methods

- `public CompleteDependencies() : System.Void`  

```csharp
public void CompleteDependencies()
	{
		if (m_HasDependencies)
		{
			m_WriteDependencies.Complete();
			m_WriteDependencies = default(JobHandle);
			m_HasDependencies = false;
		}
	}
```

- `public Dispose() : System.Void`  

```csharp
public void Dispose()
	{
		DisposeBuffers();
	}
```

- `private DisposeBuffers() : System.Void`  

```csharp
private void DisposeBuffers()
	{
		CompleteDependencies();
		NativeList<byte> nativeList = buffer;
		if (nativeList.IsCreated)
		{
			nativeList.Dispose();
		}
		buffer = nativeList;
	}
```

- `public Done(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public void Done()
	{
		m_IsDone = true;
	}
```

- `public Done() : System.Void`  

```csharp
public void Done()
	{
		m_IsDone = true;
	}
```


