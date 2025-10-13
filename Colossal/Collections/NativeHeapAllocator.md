# Colossal.Collections.NativeHeapAllocator

**Assembly:** `Colossal.Collections`  
**Namespace:** `Colossal.Collections`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

**Attributes:** `NativeContainer`, `GenerateTestsForBurstCompatibility`  

## Code

```csharp
public sealed struct NativeHeapAllocator : System.IDisposable
{
    internal Colossal.Collections.UnsafeHeapAllocator* m_HeapData;
    internal Unity.Collections.Allocator m_AllocatorLabel;

    public System.Boolean IsCreated { get; }
    public System.UInt32 MinimumAlignment { get; }
    public System.UInt32 FreeSpace { get; }
    public System.UInt32 UsedSpace { get; }
    public System.UInt32 OnePastHighestUsedAddress { get; }
    public System.UInt32 Size { get; }
    public System.Boolean Empty { get; }
    public System.Boolean Full { get; }

    public NativeHeapAllocator(System.UInt32 size, System.UInt32 minimumAlignment, Unity.Collections.Allocator allocator);
    private NativeHeapAllocator(System.UInt32 size, System.UInt32 minimumAlignment, Unity.Collections.Allocator allocator, System.Int32 disposeSentinelStackDepth);

    public Colossal.Collections.NativeHeapBlock Allocate(System.UInt32 size, System.UInt32 alignment);
    private System.Void CheckRead();
    private System.Void CheckWrite();
    public System.Void Clear();
    public System.Void Dispose();
    public System.Void Release(Colossal.Collections.NativeHeapBlock block);
    public System.Boolean Resize(System.UInt32 newSize);
}
```


## Fields

- `internal Colossal.Collections.UnsafeHeapAllocator* m_HeapData`  

```csharp
internal Colossal.Collections.UnsafeHeapAllocator* m_HeapData;
```

- `internal Unity.Collections.Allocator m_AllocatorLabel`  

```csharp
internal Unity.Collections.Allocator m_AllocatorLabel;
```


## Properties

- `public System.Boolean IsCreated { get }`  

```csharp
public System.Boolean IsCreated { get; }
```

- `public System.UInt32 MinimumAlignment { get }`  

```csharp
public System.UInt32 MinimumAlignment { get; }
```

- `public System.UInt32 FreeSpace { get }`  

```csharp
public System.UInt32 FreeSpace { get; }
```

- `public System.UInt32 UsedSpace { get }`  

```csharp
public System.UInt32 UsedSpace { get; }
```

- `public System.UInt32 OnePastHighestUsedAddress { get }`  

```csharp
public System.UInt32 OnePastHighestUsedAddress { get; }
```

- `public System.UInt32 Size { get }`  

```csharp
public System.UInt32 Size { get; }
```

- `public System.Boolean Empty { get }`  

```csharp
public System.Boolean Empty { get; }
```

- `public System.Boolean Full { get }`  

```csharp
public System.Boolean Full { get; }
```


## Constructors

- `public NativeHeapAllocator(System.UInt32 size, System.UInt32 minimumAlignment, Unity.Collections.Allocator allocator)`  

```csharp
public NativeHeapAllocator(System.UInt32 size, System.UInt32 minimumAlignment, Unity.Collections.Allocator allocator);
```

- `private NativeHeapAllocator(System.UInt32 size, System.UInt32 minimumAlignment, Unity.Collections.Allocator allocator, System.Int32 disposeSentinelStackDepth)`  

```csharp
private NativeHeapAllocator(System.UInt32 size, System.UInt32 minimumAlignment, Unity.Collections.Allocator allocator, System.Int32 disposeSentinelStackDepth);
```


## Methods

- `public Allocate(System.UInt32 size, System.UInt32 alignment = 1) : Colossal.Collections.NativeHeapBlock`  

```csharp
public Colossal.Collections.NativeHeapBlock Allocate(System.UInt32 size, System.UInt32 alignment);
```

- `private CheckRead() : System.Void`  

```csharp
private System.Void CheckRead();
```

- `private CheckWrite() : System.Void`  

```csharp
private System.Void CheckWrite();
```

- `public Clear() : System.Void`  

```csharp
public System.Void Clear();
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public Release(Colossal.Collections.NativeHeapBlock block) : System.Void`  

```csharp
public System.Void Release(Colossal.Collections.NativeHeapBlock block);
```

- `public Resize(System.UInt32 newSize) : System.Boolean`  

```csharp
public System.Boolean Resize(System.UInt32 newSize);
```


