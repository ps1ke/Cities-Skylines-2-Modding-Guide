# Colossal.OdinSerializer.BinaryDataWriter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.BaseDataWriter`  
**Implements:** `Colossal.OdinSerializer.IDataWriter`, `System.IDisposable`  

## Fields

- `private readonly System.Byte[] small_buffer`  
- `private readonly System.Byte[] buffer`  
- `private System.Int32 bufferIndex`  
- `private readonly System.Collections.Generic.Dictionary<System.Type, System.Int32> types`  
- `public System.Boolean CompressStringsTo8BitWhenPossible`  
- `private static readonly System.Collections.Generic.Dictionary<System.Type, System.Delegate> PrimitiveGetBytesMethods`  
- `private static readonly System.Collections.Generic.Dictionary<System.Type, System.Int32> PrimitiveSizes`  
- `private static readonly System.Collections.Generic.Dictionary<System.Type, System.Action<Colossal.OdinSerializer.BinaryDataWriter, System.Object>> PrimitiveArrayWriters`  

## Constructors

- `public BinaryDataWriter()`  
- `public BinaryDataWriter(System.IO.Stream stream, Colossal.OdinSerializer.SerializationContext context)`  

## Methods

- `public virtual BeginArrayNode(System.Int64 length) : System.Void`  
- `public virtual BeginReferenceNode(System.String name, System.Type type, System.Int32 id) : System.Void`  
- `public virtual BeginStructNode(System.String name, System.Type type) : System.Void`  
- `public virtual Dispose() : System.Void`  
- `public virtual EndArrayNode() : System.Void`  
- `public virtual EndNode(System.String name) : System.Void`  
- `private EnsureBufferSpace(System.Int32 space) : System.Void`  
- `public virtual FlushToStream() : System.Void`  
- `public virtual GetDataDump() : System.String`  
- `public virtual PrepareNewSerializationSession() : System.Void`  
- `private TryEnsureBufferSpace(System.Int32 space) : System.Boolean`  
- `private UNSAFE_WriteToBuffer_16_Decimal(System.Decimal value) : System.Void`  
- `private UNSAFE_WriteToBuffer_16_Guid(System.Guid value) : System.Void`  
- `private UNSAFE_WriteToBuffer_2_Char(System.Char value) : System.Void`  
- `private UNSAFE_WriteToBuffer_2_Int16(System.Int16 value) : System.Void`  
- `private UNSAFE_WriteToBuffer_2_UInt16(System.UInt16 value) : System.Void`  
- `private UNSAFE_WriteToBuffer_4_Float32(System.Single value) : System.Void`  
- `private UNSAFE_WriteToBuffer_4_Int32(System.Int32 value) : System.Void`  
- `private UNSAFE_WriteToBuffer_4_UInt32(System.UInt32 value) : System.Void`  
- `private UNSAFE_WriteToBuffer_8_Float64(System.Double value) : System.Void`  
- `private UNSAFE_WriteToBuffer_8_Int64(System.Int64 value) : System.Void`  
- `private UNSAFE_WriteToBuffer_8_UInt64(System.UInt64 value) : System.Void`  
- `public virtual WriteBoolean(System.String name, System.Boolean value) : System.Void`  
- `public virtual WriteByte(System.String name, System.Byte value) : System.Void`  
- `public virtual WriteChar(System.String name, System.Char value) : System.Void`  
- `public virtual WriteDecimal(System.String name, System.Decimal value) : System.Void`  
- `public virtual WriteDouble(System.String name, System.Double value) : System.Void`  
- `public virtual WriteExternalReference(System.String name, System.Guid guid) : System.Void`  
- `public virtual WriteExternalReference(System.String name, System.Int32 index) : System.Void`  
- `public virtual WriteExternalReference(System.String name, System.String id) : System.Void`  
- `public virtual WriteGuid(System.String name, System.Guid value) : System.Void`  
- `public virtual WriteInt16(System.String name, System.Int16 value) : System.Void`  
- `public virtual WriteInt32(System.String name, System.Int32 value) : System.Void`  
- `public virtual WriteInt64(System.String name, System.Int64 value) : System.Void`  
- `public virtual WriteInternalReference(System.String name, System.Int32 id) : System.Void`  
- `public virtual WriteNull(System.String name) : System.Void`  
- `public virtual WritePrimitiveArray<T>(T[] array) : System.Void`  
- `private static WritePrimitiveArray_bool(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o) : System.Void`  
- `private static WritePrimitiveArray_byte(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o) : System.Void`  
- `private static WritePrimitiveArray_char(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o) : System.Void`  
- `private static WritePrimitiveArray_decimal(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o) : System.Void`  
- `private static WritePrimitiveArray_double(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o) : System.Void`  
- `private static WritePrimitiveArray_float(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o) : System.Void`  
- `private static WritePrimitiveArray_Guid(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o) : System.Void`  
- `private static WritePrimitiveArray_int(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o) : System.Void`  
- `private static WritePrimitiveArray_long(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o) : System.Void`  
- `private static WritePrimitiveArray_sbyte(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o) : System.Void`  
- `private static WritePrimitiveArray_short(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o) : System.Void`  
- `private static WritePrimitiveArray_uint(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o) : System.Void`  
- `private static WritePrimitiveArray_ulong(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o) : System.Void`  
- `private static WritePrimitiveArray_ushort(Colossal.OdinSerializer.BinaryDataWriter writer, System.Object o) : System.Void`  
- `public virtual WriteSByte(System.String name, System.SByte value) : System.Void`  
- `public virtual WriteSingle(System.String name, System.Single value) : System.Void`  
- `public virtual WriteString(System.String name, System.String value) : System.Void`  
- `private WriteStringFast(System.String value) : System.Void`  
- `private WriteType(System.Type type) : System.Void`  
- `public virtual WriteUInt16(System.String name, System.UInt16 value) : System.Void`  
- `public virtual WriteUInt32(System.String name, System.UInt32 value) : System.Void`  
- `public virtual WriteUInt64(System.String name, System.UInt64 value) : System.Void`  

## Nested types

- `Colossal.OdinSerializer.BinaryDataWriter+Struct256Bit`  
- `Colossal.OdinSerializer.BinaryDataWriter+<>c`  

