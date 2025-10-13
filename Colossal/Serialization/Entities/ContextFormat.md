# Colossal.Serialization.Entities.ContextFormat

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Serialization.Entities`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct ContextFormat
{
    private Unity.Collections.LowLevel.Unsafe.UnsafeList<System.UInt32> m_Bits;

    internal ContextFormat(System.Int32 tagCount, Unity.Collections.Allocator allocator);

    internal System.Void Dispose();
    internal System.Void EnableTag(System.Int32 index);
    public System.Boolean Has<TFormatTags>(TFormatTags tag);
}
```


## Fields

- `private Unity.Collections.LowLevel.Unsafe.UnsafeList<System.UInt32> m_Bits`  

```csharp
private Unity.Collections.LowLevel.Unsafe.UnsafeList<System.UInt32> m_Bits;
```


## Constructors

- `internal ContextFormat(System.Int32 tagCount, Unity.Collections.Allocator allocator)`  

```csharp
internal ContextFormat(System.Int32 tagCount, Unity.Collections.Allocator allocator);
```


## Methods

- `internal Dispose() : System.Void`  

```csharp
internal System.Void Dispose();
```

- `internal EnableTag(System.Int32 index) : System.Void`  

```csharp
internal System.Void EnableTag(System.Int32 index);
```

- `public Has<TFormatTags>(TFormatTags tag) : System.Boolean`  

```csharp
public System.Boolean Has<TFormatTags>(TFormatTags tag);
```


