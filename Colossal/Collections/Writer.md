# Colossal.Collections.NativeParallelQueue`1+Writer

**Assembly:** `Colossal.Collections`  
**Namespace:** `Colossal.Collections`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `NativeContainer`, `NativeContainerIsAtomicWriteOnly`, `GenerateTestsForBurstCompatibility`  

## Code

```csharp
public sealed struct Writer<T>
{
    internal Colossal.Collections.NativeParallelQueueData* m_Buffer;
    internal Colossal.Collections.NativeParallelQueueBlockPoolData* m_QueuePool;
    internal System.Int32 m_HashRange;
    internal System.Int32 m_BufferSize;
    internal System.Int32 m_ThreadIndex;

    public System.Int32 HashRange { get; }

    private System.Void CheckWrite();
    public System.Void Enqueue(T value);
    public System.Void Enqueue(System.Int32 hashCode, T value);
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

- `internal System.Int32 m_ThreadIndex`  

```csharp
internal System.Int32 m_ThreadIndex;
```


## Properties

- `public System.Int32 HashRange { get }`  

```csharp
public System.Int32 HashRange { get; }
```


## Methods

- `private CheckWrite() : System.Void`  

```csharp
private System.Void CheckWrite();
```

- `public Enqueue(T value) : System.Void`  

```csharp
public System.Void Enqueue(T value);
```

- `public Enqueue(System.Int32 hashCode, T value) : System.Void`  

```csharp
public System.Void Enqueue(System.Int32 hashCode, T value);
```


