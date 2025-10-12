# Colossal.Rendering.NativeBatchProperties

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Fields

- `internal Unity.Collections.LowLevel.Unsafe.UnsafeList<Colossal.Rendering.UnsafeBatchProperty> m_Properties`  

## Constructors

- `internal NativeBatchProperties(System.Int32 propertyCount, Unity.Collections.Allocator allocator)`  

## Methods

- `internal AddProperty(System.Int32 nameID, System.Int32 sizeBytesGPU, System.Boolean builtinProperty, System.Boolean overriddenInBatch, System.Boolean globalValue, System.Int32& defaultsSize) : System.Void`  
- `public Dispose() : System.Void`  
- `internal GetDefaultOffset(System.Int32 index) : System.Int32`  
- `public GetNameID(System.Int32 index) : System.Int32`  
- `public GetSize(System.Int32 index) : System.Int32`  
- `public IsBuiltin(System.Int32 index) : System.Boolean`  
- `public IsGlobal(System.Int32 index) : System.Boolean`  

