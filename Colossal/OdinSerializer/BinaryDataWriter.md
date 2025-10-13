# Colossal.OdinSerializer.BinaryDataWriter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.BaseDataWriter`  
**Implements:** `Colossal.OdinSerializer.IDataWriter`, `System.IDisposable`  

## Code

```csharp
public class BinaryDataWriter : Colossal.OdinSerializer.BaseDataWriter, Colossal.OdinSerializer.IDataWriter, System.IDisposable
{
    private readonly System.Byte[] small_buffer;
    private readonly System.Byte[] buffer;
    private System.Int32 bufferIndex;
    private readonly System.Collections.Generic.Dictionary<System.Type, System.Int32> types;
    public System.Boolean CompressStringsTo8BitWhenPossible;
    private static readonly System.Collections.Generic.Dictionary<System.Type, System.Delegate> PrimitiveGetBytesMethods;
    private static readonly System.Collections.Generic.Dictionary<System.Type, System.Int32> PrimitiveSizes;
    private static readonly System.Collections.Generic.Dictionary<System.Type, System.Action<Colossal.OdinSerializer.BinaryDataWriter, System.Object>> PrimitiveArrayWriters;

    public BinaryDataWriter();
    public BinaryDataWriter(System.IO.Stream stream, Colossal.OdinSerializer.SerializationContext context);

    public virtual System.Void BeginArrayNode(System.Int64 length);
    public virtual System.Void BeginReferenceNode(System.String name, System.Type type, System.Int32 id);
    public virtual System.Void BeginStructNode(System.String name, System.Type type);
    public virtual System.Void Dispose();
    public virtual System.Void EndArrayNode();
    public virtual System.Void EndNode(System.String name);
    private System.Void EnsureBufferSpace(System.Int32 space);
    public virtual System.Void FlushToStream();
    public virtual System.String GetDataDump();
    public virtual System.Void PrepareNewSerializationSession();
    private System.Boolean TryEnsureBufferSpace(System.Int32 space);
    private System.Void UNSAFE_WriteToBuffer_16_Decimal(System.Decimal value);
    private System.Void UNSAFE_WriteToBuffer_16_Guid(System.Guid value);
    private System.Void UNSAFE_WriteToBuffer_2_Char(System.Char value);
    private System.Void UNSAFE_WriteToBuffer_2_Int16(System.Int16 value);
    private System.Void UNSAFE_WriteToBuffer_2_UInt16(System.UInt16 value);
    private System.Void UNSAFE_WriteToBuffer_4_Float32(System.Single value);
    private System.Void UNSAFE_WriteToBuffer_4_Int32(System.Int32 value);
    private System.Void UNSAFE_WriteToBuffer_4_UInt32(System.UInt32 value);
    private System.Void UNSAFE_WriteToBuffer_8_Float64(System.Double value);
    private System.Void UNSAFE_WriteToBuffer_8_Int64(System.Int64 value);
    private System.Void UNSAFE_WriteToBuffer_8_UInt64(System.UInt64 value);
    public virtual System.Void WriteBoolean(System.String name, System.Boolean value);
    public virtual System.Void WriteByte(System.String name, System.Byte value);
    public virtual System.Void WriteChar(System.String name, System.Char value);
    public virtual System.Void WriteDecimal(System.String name, System.Decimal value);
    public virtual System.Void WriteDouble(System.String name, System.Double value);
    public virtual System.Void WriteExternalReference(System.String name, System.Guid guid);
    public virtual System.Void WriteExternalReference(System.String name, System.Int32 index);
    public virtual System.Void WriteExternalReference(System.String name, System.String id);
    public virtual System.Void WriteGuid(System.String name, System.Guid value);
    public virtual System.Void WriteInt16(System.String name, System.Int16 value);
    public virtual System.Void WriteInt32(System.String name, System.Int32 value);
    public virtual System.Void WriteInt64(System.String name, System.Int64 value);
    public virtual System.Void WriteInternalReference(System.String name, System.Int32 id);
    public virtual System.Void WriteNull(System.String name);
    public virtual System.Void WritePrimitiveArray<T>(T[] array);
    private static System.Void WritePrimitiveArray_bool(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o);
    private static System.Void WritePrimitiveArray_byte(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o);
    private static System.Void WritePrimitiveArray_char(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o);
    private static System.Void WritePrimitiveArray_decimal(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o);
    private static System.Void WritePrimitiveArray_double(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o);
    private static System.Void WritePrimitiveArray_float(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o);
    private static System.Void WritePrimitiveArray_Guid(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o);
    private static System.Void WritePrimitiveArray_int(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o);
    private static System.Void WritePrimitiveArray_long(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o);
    private static System.Void WritePrimitiveArray_sbyte(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o);
    private static System.Void WritePrimitiveArray_short(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o);
    private static System.Void WritePrimitiveArray_uint(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o);
    private static System.Void WritePrimitiveArray_ulong(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o);
    private static System.Void WritePrimitiveArray_ushort(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o);
    public virtual System.Void WriteSByte(System.String name, System.SByte value);
    public virtual System.Void WriteSingle(System.String name, System.Single value);
    public virtual System.Void WriteString(System.String name, System.String value);
    private System.Void WriteStringFast(System.String value);
    private System.Void WriteType(System.Type type);
    public virtual System.Void WriteUInt16(System.String name, System.UInt16 value);
    public virtual System.Void WriteUInt32(System.String name, System.UInt32 value);
    public virtual System.Void WriteUInt64(System.String name, System.UInt64 value);
}
```


## Fields

- `private readonly System.Byte[] small_buffer`  

```csharp
private readonly System.Byte[] small_buffer;
```

- `private readonly System.Byte[] buffer`  

```csharp
private readonly System.Byte[] buffer;
```

- `private System.Int32 bufferIndex`  

```csharp
private System.Int32 bufferIndex;
```

- `private readonly System.Collections.Generic.Dictionary<System.Type, System.Int32> types`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.Type, System.Int32> types;
```

- `public System.Boolean CompressStringsTo8BitWhenPossible`  

```csharp
public System.Boolean CompressStringsTo8BitWhenPossible;
```

- `private static readonly System.Collections.Generic.Dictionary<System.Type, System.Delegate> PrimitiveGetBytesMethods`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.Type, System.Delegate> PrimitiveGetBytesMethods;
```

- `private static readonly System.Collections.Generic.Dictionary<System.Type, System.Int32> PrimitiveSizes`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.Type, System.Int32> PrimitiveSizes;
```

- `private static readonly System.Collections.Generic.Dictionary<System.Type, System.Action<Colossal.OdinSerializer.BinaryDataWriter, System.Object>> PrimitiveArrayWriters`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.Type, System.Action<Colossal.OdinSerializer.BinaryDataWriter, System.Object>> PrimitiveArrayWriters;
```


## Constructors

- `public BinaryDataWriter()`  

```csharp
public BinaryDataWriter();
```

- `public BinaryDataWriter(System.IO.Stream stream, Colossal.OdinSerializer.SerializationContext context)`  

```csharp
public BinaryDataWriter(System.IO.Stream stream, Colossal.OdinSerializer.SerializationContext context);
```


## Methods

- `public virtual BeginArrayNode(System.Int64 length) : System.Void`  

```csharp
public virtual System.Void BeginArrayNode(System.Int64 length);
```

- `public virtual BeginReferenceNode(System.String name, System.Type type, System.Int32 id) : System.Void`  

```csharp
public virtual System.Void BeginReferenceNode(System.String name, System.Type type, System.Int32 id);
```

- `public virtual BeginStructNode(System.String name, System.Type type) : System.Void`  

```csharp
public virtual System.Void BeginStructNode(System.String name, System.Type type);
```

- `public virtual Dispose() : System.Void`  

```csharp
public virtual System.Void Dispose();
```

- `public virtual EndArrayNode() : System.Void`  

```csharp
public virtual System.Void EndArrayNode();
```

- `public virtual EndNode(System.String name) : System.Void`  

```csharp
public virtual System.Void EndNode(System.String name);
```

- `private EnsureBufferSpace(System.Int32 space) : System.Void`  

```csharp
private System.Void EnsureBufferSpace(System.Int32 space);
```

- `public virtual FlushToStream() : System.Void`  

```csharp
public virtual System.Void FlushToStream();
```

- `public virtual GetDataDump() : System.String`  

```csharp
public virtual System.String GetDataDump();
```

- `public virtual PrepareNewSerializationSession() : System.Void`  

```csharp
public virtual System.Void PrepareNewSerializationSession();
```

- `private TryEnsureBufferSpace(System.Int32 space) : System.Boolean`  

```csharp
private System.Boolean TryEnsureBufferSpace(System.Int32 space);
```

- `private UNSAFE_WriteToBuffer_16_Decimal(System.Decimal value) : System.Void`  

```csharp
private System.Void UNSAFE_WriteToBuffer_16_Decimal(System.Decimal value);
```

- `private UNSAFE_WriteToBuffer_16_Guid(System.Guid value) : System.Void`  

```csharp
private System.Void UNSAFE_WriteToBuffer_16_Guid(System.Guid value);
```

- `private UNSAFE_WriteToBuffer_2_Char(System.Char value) : System.Void`  

```csharp
private System.Void UNSAFE_WriteToBuffer_2_Char(System.Char value);
```

- `private UNSAFE_WriteToBuffer_2_Int16(System.Int16 value) : System.Void`  

```csharp
private System.Void UNSAFE_WriteToBuffer_2_Int16(System.Int16 value);
```

- `private UNSAFE_WriteToBuffer_2_UInt16(System.UInt16 value) : System.Void`  

```csharp
private System.Void UNSAFE_WriteToBuffer_2_UInt16(System.UInt16 value);
```

- `private UNSAFE_WriteToBuffer_4_Float32(System.Single value) : System.Void`  

```csharp
private System.Void UNSAFE_WriteToBuffer_4_Float32(System.Single value);
```

- `private UNSAFE_WriteToBuffer_4_Int32(System.Int32 value) : System.Void`  

```csharp
private System.Void UNSAFE_WriteToBuffer_4_Int32(System.Int32 value);
```

- `private UNSAFE_WriteToBuffer_4_UInt32(System.UInt32 value) : System.Void`  

```csharp
private System.Void UNSAFE_WriteToBuffer_4_UInt32(System.UInt32 value);
```

- `private UNSAFE_WriteToBuffer_8_Float64(System.Double value) : System.Void`  

```csharp
private System.Void UNSAFE_WriteToBuffer_8_Float64(System.Double value);
```

- `private UNSAFE_WriteToBuffer_8_Int64(System.Int64 value) : System.Void`  

```csharp
private System.Void UNSAFE_WriteToBuffer_8_Int64(System.Int64 value);
```

- `private UNSAFE_WriteToBuffer_8_UInt64(System.UInt64 value) : System.Void`  

```csharp
private System.Void UNSAFE_WriteToBuffer_8_UInt64(System.UInt64 value);
```

- `public virtual WriteBoolean(System.String name, System.Boolean value) : System.Void`  

```csharp
public virtual System.Void WriteBoolean(System.String name, System.Boolean value);
```

- `public virtual WriteByte(System.String name, System.Byte value) : System.Void`  

```csharp
public virtual System.Void WriteByte(System.String name, System.Byte value);
```

- `public virtual WriteChar(System.String name, System.Char value) : System.Void`  

```csharp
public virtual System.Void WriteChar(System.String name, System.Char value);
```

- `public virtual WriteDecimal(System.String name, System.Decimal value) : System.Void`  

```csharp
public virtual System.Void WriteDecimal(System.String name, System.Decimal value);
```

- `public virtual WriteDouble(System.String name, System.Double value) : System.Void`  

```csharp
public virtual System.Void WriteDouble(System.String name, System.Double value);
```

- `public virtual WriteExternalReference(System.String name, System.Guid guid) : System.Void`  

```csharp
public virtual System.Void WriteExternalReference(System.String name, System.Guid guid);
```

- `public virtual WriteExternalReference(System.String name, System.Int32 index) : System.Void`  

```csharp
public virtual System.Void WriteExternalReference(System.String name, System.Int32 index);
```

- `public virtual WriteExternalReference(System.String name, System.String id) : System.Void`  

```csharp
public virtual System.Void WriteExternalReference(System.String name, System.String id);
```

- `public virtual WriteGuid(System.String name, System.Guid value) : System.Void`  

```csharp
public virtual System.Void WriteGuid(System.String name, System.Guid value);
```

- `public virtual WriteInt16(System.String name, System.Int16 value) : System.Void`  

```csharp
public virtual System.Void WriteInt16(System.String name, System.Int16 value);
```

- `public virtual WriteInt32(System.String name, System.Int32 value) : System.Void`  

```csharp
public virtual System.Void WriteInt32(System.String name, System.Int32 value);
```

- `public virtual WriteInt64(System.String name, System.Int64 value) : System.Void`  

```csharp
public virtual System.Void WriteInt64(System.String name, System.Int64 value);
```

- `public virtual WriteInternalReference(System.String name, System.Int32 id) : System.Void`  

```csharp
public virtual System.Void WriteInternalReference(System.String name, System.Int32 id);
```

- `public virtual WriteNull(System.String name) : System.Void`  

```csharp
public virtual System.Void WriteNull(System.String name);
```

- `public virtual WritePrimitiveArray<T>(T[] array) : System.Void`  

```csharp
public virtual System.Void WritePrimitiveArray<T>(T[] array);
```

- `private static WritePrimitiveArray_bool(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o) : System.Void`  

```csharp
private static System.Void WritePrimitiveArray_bool(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o);
```

- `private static WritePrimitiveArray_byte(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o) : System.Void`  

```csharp
private static System.Void WritePrimitiveArray_byte(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o);
```

- `private static WritePrimitiveArray_char(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o) : System.Void`  

```csharp
private static System.Void WritePrimitiveArray_char(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o);
```

- `private static WritePrimitiveArray_decimal(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o) : System.Void`  

```csharp
private static System.Void WritePrimitiveArray_decimal(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o);
```

- `private static WritePrimitiveArray_double(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o) : System.Void`  

```csharp
private static System.Void WritePrimitiveArray_double(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o);
```

- `private static WritePrimitiveArray_float(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o) : System.Void`  

```csharp
private static System.Void WritePrimitiveArray_float(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o);
```

- `private static WritePrimitiveArray_Guid(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o) : System.Void`  

```csharp
private static System.Void WritePrimitiveArray_Guid(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o);
```

- `private static WritePrimitiveArray_int(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o) : System.Void`  

```csharp
private static System.Void WritePrimitiveArray_int(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o);
```

- `private static WritePrimitiveArray_long(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o) : System.Void`  

```csharp
private static System.Void WritePrimitiveArray_long(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o);
```

- `private static WritePrimitiveArray_sbyte(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o) : System.Void`  

```csharp
private static System.Void WritePrimitiveArray_sbyte(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o);
```

- `private static WritePrimitiveArray_short(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o) : System.Void`  

```csharp
private static System.Void WritePrimitiveArray_short(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o);
```

- `private static WritePrimitiveArray_uint(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o) : System.Void`  

```csharp
private static System.Void WritePrimitiveArray_uint(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o);
```

- `private static WritePrimitiveArray_ulong(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o) : System.Void`  

```csharp
private static System.Void WritePrimitiveArray_ulong(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o);
```

- `private static WritePrimitiveArray_ushort(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o) : System.Void`  

```csharp
private static System.Void WritePrimitiveArray_ushort(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o);
```

- `public virtual WriteSByte(System.String name, System.SByte value) : System.Void`  

```csharp
public virtual System.Void WriteSByte(System.String name, System.SByte value);
```

- `public virtual WriteSingle(System.String name, System.Single value) : System.Void`  

```csharp
public virtual System.Void WriteSingle(System.String name, System.Single value);
```

- `public virtual WriteString(System.String name, System.String value) : System.Void`  

```csharp
public virtual System.Void WriteString(System.String name, System.String value);
```

- `private WriteStringFast(System.String value) : System.Void`  

```csharp
private System.Void WriteStringFast(System.String value);
```

- `private WriteType(System.Type type) : System.Void`  

```csharp
private System.Void WriteType(System.Type type);
```

- `public virtual WriteUInt16(System.String name, System.UInt16 value) : System.Void`  

```csharp
public virtual System.Void WriteUInt16(System.String name, System.UInt16 value);
```

- `public virtual WriteUInt32(System.String name, System.UInt32 value) : System.Void`  

```csharp
public virtual System.Void WriteUInt32(System.String name, System.UInt32 value);
```

- `public virtual WriteUInt64(System.String name, System.UInt64 value) : System.Void`  

```csharp
public virtual System.Void WriteUInt64(System.String name, System.UInt64 value);
```


## Nested types

- `Colossal.OdinSerializer.BinaryDataWriter+Struct256Bit`  
- `Colossal.OdinSerializer.BinaryDataWriter+<>c`  

