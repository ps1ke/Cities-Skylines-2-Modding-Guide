# Colossal.Collections.UnsafeLinearAllocator

**Assembly:** `Colossal.Collections`  
**Namespace:** `Colossal.Collections`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Collections.AllocatorManager+IAllocator`, `System.IDisposable`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct UnsafeLinearAllocator : Unity.Collections.AllocatorManager+IAllocator, System.IDisposable
{
    private Unity.Collections.LowLevel.Unsafe.UnsafeList<Colossal.Collections.UnsafeLinearAllocator+Buffer> m_Buffers;
    private Unity.Collections.AllocatorManager+AllocatorHandle m_Handle;
    private System.UInt32 m_MaxUsed;
    private System.UInt32 m_MaxSize;
    private System.Boolean m_LastBufferUsed;
    private System.UInt32 <Used>k__BackingField;
    private System.UInt32 <Size>k__BackingField;

    public System.UInt32 Used { get; private set; }
    public System.UInt32 Size { get; private set; }
    public Unity.Collections.AllocatorManager+TryFunction Function { get; }
    public Unity.Collections.AllocatorManager+AllocatorHandle Handle { get; set; }
    public Unity.Collections.Allocator ToAllocator { get; }
    public System.Boolean IsCustomAllocator { get; }
    public System.Boolean IsAutoDispose { get; }

    public System.Void Dispose();
    public System.Void Initialize(System.UInt32 initialSize);
    public System.Void Rewind(System.Boolean updateSize);
    public System.Int32 Try(Unity.Collections.AllocatorManager+Block& block);
    internal static System.Int32 Try(System.IntPtr state, Unity.Collections.AllocatorManager+Block& block);
    public static System.Int32 Try$BurstManaged(System.IntPtr state, Unity.Collections.AllocatorManager+Block& block);
}
```


## Fields

- `private Unity.Collections.LowLevel.Unsafe.UnsafeList<Colossal.Collections.UnsafeLinearAllocator+Buffer> m_Buffers`  

```csharp
private Unity.Collections.LowLevel.Unsafe.UnsafeList<Colossal.Collections.UnsafeLinearAllocator+Buffer> m_Buffers;
```

- `private Unity.Collections.AllocatorManager+AllocatorHandle m_Handle`  

```csharp
private Unity.Collections.AllocatorManager+AllocatorHandle m_Handle;
```

- `private System.UInt32 m_MaxUsed`  

```csharp
private System.UInt32 m_MaxUsed;
```

- `private System.UInt32 m_MaxSize`  

```csharp
private System.UInt32 m_MaxSize;
```

- `private System.Boolean m_LastBufferUsed`  

```csharp
private System.Boolean m_LastBufferUsed;
```

- `private System.UInt32 <Used>k__BackingField`  

```csharp
private System.UInt32 <Used>k__BackingField;
```

- `private System.UInt32 <Size>k__BackingField`  

```csharp
private System.UInt32 <Size>k__BackingField;
```


## Properties

- `public System.UInt32 Used { get; private set }`  

```csharp
public System.UInt32 Used { get; private set; }
```

- `public System.UInt32 Size { get; private set }`  

```csharp
public System.UInt32 Size { get; private set; }
```

- `public Unity.Collections.AllocatorManager+TryFunction Function { get }`  

```csharp
public Unity.Collections.AllocatorManager+TryFunction Function { get; }
```

- `public Unity.Collections.AllocatorManager+AllocatorHandle Handle { get; set }`  

```csharp
public Unity.Collections.AllocatorManager+AllocatorHandle Handle { get; set; }
```

- `public Unity.Collections.Allocator ToAllocator { get }`  

```csharp
public Unity.Collections.Allocator ToAllocator { get; }
```

- `public System.Boolean IsCustomAllocator { get }`  

```csharp
public System.Boolean IsCustomAllocator { get; }
```

- `public System.Boolean IsAutoDispose { get }`  

```csharp
public System.Boolean IsAutoDispose { get; }
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public Initialize(System.UInt32 initialSize) : System.Void`  

```csharp
public System.Void Initialize(System.UInt32 initialSize);
```

- `public Rewind(System.Boolean updateSize = False) : System.Void`  

```csharp
public System.Void Rewind(System.Boolean updateSize);
```

- `public Try(Unity.Collections.AllocatorManager+Block& block) : System.Int32`  

```csharp
public System.Int32 Try(Unity.Collections.AllocatorManager+Block& block);
```

- `internal static Try(System.IntPtr state, Unity.Collections.AllocatorManager+Block& block) : System.Int32`  

```csharp
internal static System.Int32 Try(System.IntPtr state, Unity.Collections.AllocatorManager+Block& block);
```

- `public static Try$BurstManaged(System.IntPtr state, Unity.Collections.AllocatorManager+Block& block) : System.Int32`  

```csharp
public static System.Int32 Try$BurstManaged(System.IntPtr state, Unity.Collections.AllocatorManager+Block& block);
```


## Nested types

- `Colossal.Collections.UnsafeLinearAllocator+Buffer`  
- `Colossal.Collections.UnsafeLinearAllocator+Colossal.Collections.Try_000000FB$PostfixBurstDelegate`  
- `Colossal.Collections.UnsafeLinearAllocator+Colossal.Collections.Try_000000FB$BurstDirectCall`  

