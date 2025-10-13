# Colossal.NativePerThreadSumInt+Concurrent

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `NativeContainer`, `NativeContainerIsAtomicWriteOnly`  

## Code

```csharp
public sealed struct Concurrent
{
    internal System.Int32* m_Counter;
    internal System.Int32 m_ThreadIndex;

    public System.Void Add(System.Int32 x);
}
```


## Fields

- `internal System.Int32* m_Counter`  

```csharp
internal System.Int32* m_Counter;
```

- `internal System.Int32 m_ThreadIndex`  

```csharp
internal System.Int32 m_ThreadIndex;
```


## Methods

- `public Add(System.Int32 x) : System.Void`  

```csharp
public System.Void Add(System.Int32 x);
```


