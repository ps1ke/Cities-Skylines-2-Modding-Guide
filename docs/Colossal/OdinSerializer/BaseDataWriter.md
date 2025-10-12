# Colossal.OdinSerializer.BaseDataWriter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class abstract public  

**Base:** `Colossal.OdinSerializer.BaseDataReaderWriter`  
**Implements:** `Colossal.OdinSerializer.IDataWriter`, `System.IDisposable`  

## Fields

- `private Colossal.OdinSerializer.SerializationContext context`  
- `private System.IO.Stream stream`  

## Properties

- `public System.IO.Stream Stream { get; set }`  
- `public Colossal.OdinSerializer.SerializationContext Context { get; set }`  

## Constructors

- `protected BaseDataWriter(System.IO.Stream stream, Colossal.OdinSerializer.SerializationContext context)`  

## Methods

- `public abstract BeginArrayNode(System.Int64 length) : System.Void`  
- `public abstract BeginReferenceNode(System.String name, System.Type type, System.Int32 id) : System.Void`  
- `public abstract BeginStructNode(System.String name, System.Type type) : System.Void`  
- `public abstract Dispose() : System.Void`  
- `public abstract EndArrayNode() : System.Void`  
- `public abstract EndNode(System.String name) : System.Void`  
- `public virtual FlushToStream() : System.Void`  
- `public abstract GetDataDump() : System.String`  
- `public virtual PrepareNewSerializationSession() : System.Void`  
- `public abstract WriteBoolean(System.String name, System.Boolean value) : System.Void`  
- `public abstract WriteByte(System.String name, System.Byte value) : System.Void`  
- `public abstract WriteChar(System.String name, System.Char value) : System.Void`  
- `public abstract WriteDecimal(System.String name, System.Decimal value) : System.Void`  
- `public abstract WriteDouble(System.String name, System.Double value) : System.Void`  
- `public abstract WriteExternalReference(System.String name, System.Int32 index) : System.Void`  
- `public abstract WriteExternalReference(System.String name, System.Guid guid) : System.Void`  
- `public abstract WriteExternalReference(System.String name, System.String id) : System.Void`  
- `public abstract WriteGuid(System.String name, System.Guid value) : System.Void`  
- `public abstract WriteInt16(System.String name, System.Int16 value) : System.Void`  
- `public abstract WriteInt32(System.String name, System.Int32 value) : System.Void`  
- `public abstract WriteInt64(System.String name, System.Int64 value) : System.Void`  
- `public abstract WriteInternalReference(System.String name, System.Int32 id) : System.Void`  
- `public abstract WriteNull(System.String name) : System.Void`  
- `public abstract WritePrimitiveArray<T>(T[] array) : System.Void`  
- `public abstract WriteSByte(System.String name, System.SByte value) : System.Void`  
- `public abstract WriteSingle(System.String name, System.Single value) : System.Void`  
- `public abstract WriteString(System.String name, System.String value) : System.Void`  
- `public abstract WriteUInt16(System.String name, System.UInt16 value) : System.Void`  
- `public abstract WriteUInt32(System.String name, System.UInt32 value) : System.Void`  
- `public abstract WriteUInt64(System.String name, System.UInt64 value) : System.Void`  

