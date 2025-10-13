# Colossal.Collections.NativeParallelQueue`1+Reader

**Assembly:** `Colossal.Collections`  
**Namespace:** `Colossal.Collections`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `NativeContainer`, `NativeContainerSupportsMinMaxWriteRestriction`, `GenerateTestsForBurstCompatibility`  

## Code

```csharp
public sealed struct Reader<T>
{
    internal Colossal.Collections.NativeParallelQueueData* m_Buffer;
    internal Colossal.Collections.NativeParallelQueueBlockPoolData* m_QueuePool;
    internal System.Int32 m_HashRange;
    internal System.Int32 m_BufferSize;

    public System.Int32 HashRange { get; }

    private System.Void CheckRead(System.Int32 hashIndex);
    private System.Void CheckReadNotEmpty(System.Int32 hashIndex);
    private System.Void CheckWrite(System.Int32 hashIndex);
    public T Dequeue(System.Int32 hashIndex);
    public System.Int32 GetCount(System.Int32 hashIndex);
    public Colossal.Collections.NativeParallelQueue<T> GetEnumerator(System.Int32 hashIndex);
    public System.Boolean IsEmpty(System.Int32 hashIndex);
    public T Peek(System.Int32 hashIndex);
    public Unity.Collections.NativeArray<T> ToArray(System.Int32 hashIndex, Unity.Collections.AllocatorManager+AllocatorHandle allocator);
    public System.Boolean TryDequeue(System.Int32 hashIndex, T& item);
}
```


## Fields

- `internal Colossal.Collections.NativeParallelQueueData* m_Buffer`  

```csharp
internal Colossal.Collections.NativeParallelQueueData* m_Buffer;
```

- `internal Colossal.Collections.NativeParallelQueueBlockPoolData* m_QueuePool`  

```csharp
internal Colossal.Collections.NativeParallelQueueBlockPoolData* m_QueuePool;
```

- `internal System.Int32 m_HashRange`  

```csharp
internal System.Int32 m_HashRange;
```

- `internal System.Int32 m_BufferSize`  

```csharp
internal System.Int32 m_BufferSize;
```


## Properties

- `public System.Int32 HashRange { get }`  

```csharp
public System.Int32 HashRange { get; }
```


## Methods

- `private CheckRead(System.Int32 hashIndex) : System.Void`  

```csharp
private System.Void CheckRead(System.Int32 hashIndex);
```

- `private CheckReadNotEmpty(System.Int32 hashIndex) : System.Void`  

```csharp
private System.Void CheckReadNotEmpty(System.Int32 hashIndex);
```

- `private CheckWrite(System.Int32 hashIndex) : System.Void`  

```csharp
private System.Void CheckWrite(System.Int32 hashIndex);
```

- `public Dequeue(System.Int32 hashIndex) : T`  

```csharp
public T Dequeue(System.Int32 hashIndex);
```

- `public GetCount(System.Int32 hashIndex) : System.Int32`  

```csharp
public System.Int32 GetCount(System.Int32 hashIndex);
```

- `public GetEnumerator(System.Int32 hashIndex) : Colossal.Collections.NativeParallelQueue<T>`  

```csharp
public Colossal.Collections.NativeParallelQueue<T> GetEnumerator(System.Int32 hashIndex);
```

- `public IsEmpty(System.Int32 hashIndex) : System.Boolean`  

```csharp
public System.Boolean IsEmpty(System.Int32 hashIndex);
```

- `public Peek(System.Int32 hashIndex) : T`  

```csharp
public T Peek(System.Int32 hashIndex);
```

- `public ToArray(System.Int32 hashIndex, Unity.Collections.AllocatorManager+AllocatorHandle allocator) : Unity.Collections.NativeArray<T>`  

```csharp
public Unity.Collections.NativeArray<T> ToArray(System.Int32 hashIndex, Unity.Collections.AllocatorManager+AllocatorHandle allocator);
```

- `public TryDequeue(System.Int32 hashIndex, T& item) : System.Boolean`  

```csharp
public System.Boolean TryDequeue(System.Int32 hashIndex, T& item);
```


