# Colossal.OdinSerializer.SerializationNodeDataWriter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.BaseDataWriter`  
**Implements:** `Colossal.OdinSerializer.IDataWriter`, `System.IDisposable`  

## Fields

- `private System.Collections.Generic.List<Colossal.OdinSerializer.SerializationNode> nodes`  
- `private System.Collections.Generic.Dictionary<System.Type, System.Delegate> primitiveTypeWriters`  

## Properties

- `public System.Collections.Generic.List<Colossal.OdinSerializer.SerializationNode> Nodes { get; set }`  
- `public System.IO.Stream Stream { get; set }`  

## Constructors

- `public SerializationNodeDataWriter(Colossal.OdinSerializer.SerializationContext context)`  

## Methods

- `public virtual BeginArrayNode(System.Int64 length) : System.Void`  
- `public virtual BeginReferenceNode(System.String name, System.Type type, System.Int32 id) : System.Void`  
- `public virtual BeginStructNode(System.String name, System.Type type) : System.Void`  
- `public virtual Dispose() : System.Void`  
- `public virtual EndArrayNode() : System.Void`  
- `public virtual EndNode(System.String name) : System.Void`  
- `public virtual FlushToStream() : System.Void`  
- `public virtual GetDataDump() : System.String`  
- `public virtual PrepareNewSerializationSession() : System.Void`  
- `public virtual WriteBoolean(System.String name, System.Boolean value) : System.Void`  
- `public virtual WriteByte(System.String name, System.Byte value) : System.Void`  
- `public virtual WriteChar(System.String name, System.Char value) : System.Void`  
- `public virtual WriteDecimal(System.String name, System.Decimal value) : System.Void`  
- `public virtual WriteDouble(System.String name, System.Double value) : System.Void`  
- `public virtual WriteExternalReference(System.String name, System.Guid guid) : System.Void`  
- `public virtual WriteExternalReference(System.String name, System.String id) : System.Void`  
- `public virtual WriteExternalReference(System.String name, System.Int32 index) : System.Void`  
- `public virtual WriteGuid(System.String name, System.Guid value) : System.Void`  
- `public virtual WriteInt16(System.String name, System.Int16 value) : System.Void`  
- `public virtual WriteInt32(System.String name, System.Int32 value) : System.Void`  
- `public virtual WriteInt64(System.String name, System.Int64 value) : System.Void`  
- `public virtual WriteInternalReference(System.String name, System.Int32 id) : System.Void`  
- `public virtual WriteNull(System.String name) : System.Void`  
- `public virtual WritePrimitiveArray<T>(T[] array) : System.Void`  
- `public virtual WriteSByte(System.String name, System.SByte value) : System.Void`  
- `public virtual WriteSingle(System.String name, System.Single value) : System.Void`  
- `public virtual WriteString(System.String name, System.String value) : System.Void`  
- `public virtual WriteUInt16(System.String name, System.UInt16 value) : System.Void`  
- `public virtual WriteUInt32(System.String name, System.UInt32 value) : System.Void`  
- `public virtual WriteUInt64(System.String name, System.UInt64 value) : System.Void`  

