# Colossal.Collections.NativeAccumulator`1+ParallelWriter

**Assembly:** `Colossal.Collections`  
**Namespace:** `Colossal.Collections`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `NativeContainer`, `NativeContainerIsAtomicWriteOnly`, `GenerateTestsForBurstCompatibility`  

## Code

```csharp
public sealed struct ParallelWriter<T>
{
    internal System.Byte* m_Buffer;
    internal System.Int32 m_ThreadDataSize;
    internal System.Int32 m_ValueCount;
    internal System.Int32 m_ThreadIndex;

    public System.Void Accumulate(T value);
    public System.Void Accumulate(System.Int32 index, T value);
    private System.Void CheckIndex(System.Int32 index);
    private System.Void CheckWrite();
}
```


## Fields

- `internal System.Byte* m_Buffer`  

```csharp
internal System.Byte* m_Buffer;
```

- `internal System.Int32 m_ThreadDataSize`  

```csharp
internal System.Int32 m_ThreadDataSize;
```

- `internal System.Int32 m_ValueCount`  

```csharp
internal System.Int32 m_ValueCount;
```

- `internal System.Int32 m_ThreadIndex`  

```csharp
internal System.Int32 m_ThreadIndex;
```


## Methods

- `public Accumulate(T value) : System.Void`  

```csharp
public System.Void Accumulate(T value);
```

- `public Accumulate(System.Int32 index, T value) : System.Void`  

```csharp
public System.Void Accumulate(System.Int32 index, T value);
```

- `private CheckIndex(System.Int32 index) : System.Void`  

```csharp
private System.Void CheckIndex(System.Int32 index);
```

- `private CheckWrite() : System.Void`  

```csharp
private System.Void CheckWrite();
```


