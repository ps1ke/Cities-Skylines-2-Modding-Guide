# Colossal.Rendering.NativeBatchProperties

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public sealed struct NativeBatchProperties : System.IDisposable
{
    internal Unity.Collections.LowLevel.Unsafe.UnsafeList<Colossal.Rendering.UnsafeBatchProperty> m_Properties;

    internal NativeBatchProperties(System.Int32 propertyCount, Unity.Collections.Allocator allocator);

    internal System.Void AddProperty(System.Int32 nameID, System.Int32 sizeBytesGPU, System.Boolean builtinProperty, System.Boolean overriddenInBatch, System.Boolean globalValue, System.Int32& defaultsSize);
    public System.Void Dispose();
    internal System.Int32 GetDefaultOffset(System.Int32 index);
    public System.Int32 GetNameID(System.Int32 index);
    public System.Int32 GetSize(System.Int32 index);
    public System.Boolean IsBuiltin(System.Int32 index);
    public System.Boolean IsGlobal(System.Int32 index);
}
```


## Fields

- `internal Unity.Collections.LowLevel.Unsafe.UnsafeList<Colossal.Rendering.UnsafeBatchProperty> m_Properties`  

```csharp
internal Unity.Collections.LowLevel.Unsafe.UnsafeList<Colossal.Rendering.UnsafeBatchProperty> m_Properties;
```


## Constructors

- `internal NativeBatchProperties(System.Int32 propertyCount, Unity.Collections.Allocator allocator)`  

```csharp
internal NativeBatchProperties(System.Int32 propertyCount, Unity.Collections.Allocator allocator);
```


## Methods

- `internal AddProperty(System.Int32 nameID, System.Int32 sizeBytesGPU, System.Boolean builtinProperty, System.Boolean overriddenInBatch, System.Boolean globalValue, System.Int32& defaultsSize) : System.Void`  

```csharp
internal System.Void AddProperty(System.Int32 nameID, System.Int32 sizeBytesGPU, System.Boolean builtinProperty, System.Boolean overriddenInBatch, System.Boolean globalValue, System.Int32& defaultsSize);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `internal GetDefaultOffset(System.Int32 index) : System.Int32`  

```csharp
internal System.Int32 GetDefaultOffset(System.Int32 index);
```

- `public GetNameID(System.Int32 index) : System.Int32`  

```csharp
public System.Int32 GetNameID(System.Int32 index);
```

- `public GetSize(System.Int32 index) : System.Int32`  

```csharp
public System.Int32 GetSize(System.Int32 index);
```

- `public IsBuiltin(System.Int32 index) : System.Boolean`  

```csharp
public System.Boolean IsBuiltin(System.Int32 index);
```

- `public IsGlobal(System.Int32 index) : System.Boolean`  

```csharp
public System.Boolean IsGlobal(System.Int32 index);
```


