# Colossal.Collections.NativeParallelQueue`1+Enumerator

**Assembly:** `Colossal.Collections`  
**Namespace:** `Colossal.Collections`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.Collections.Generic.IEnumerator<T>`, `System.IDisposable`, `System.Collections.IEnumerator`  

**Attributes:** `NativeContainer`, `NativeContainerIsReadOnly`  

## Code

```csharp
public sealed struct Enumerator<T> : System.Collections.Generic.IEnumerator<T>, System.IDisposable, System.Collections.IEnumerator
{
    internal Colossal.Collections.NativeParallelQueueData* m_Buffer;
    internal Colossal.Collections.NativeParallelQueueBlockHeader* m_Block;
    internal System.Int32 m_CurrentRead;

    public T Current { get; }
    private System.Object System.Collections.IEnumerator.Current { private get; }

    public System.Void Dispose();
    public System.Boolean MoveNext();
    public System.Void Reset();
}
```


## Fields

- `internal Colossal.Collections.NativeParallelQueueData* m_Buffer`  

```csharp
internal Colossal.Collections.NativeParallelQueueData* m_Buffer;
```

- `internal Colossal.Collections.NativeParallelQueueBlockHeader* m_Block`  

```csharp
internal Colossal.Collections.NativeParallelQueueBlockHeader* m_Block;
```

- `internal System.Int32 m_CurrentRead`  

```csharp
internal System.Int32 m_CurrentRead;
```


## Properties

- `public T Current { get }`  

```csharp
public T Current { get; }
```

- `private System.Object System.Collections.IEnumerator.Current { private get }`  

```csharp
private System.Object System.Collections.IEnumerator.Current { private get; }
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public MoveNext() : System.Boolean`  

```csharp
public System.Boolean MoveNext();
```

- `public Reset() : System.Void`  

```csharp
public System.Void Reset();
```


