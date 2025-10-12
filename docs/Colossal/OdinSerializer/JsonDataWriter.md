# Colossal.OdinSerializer.JsonDataWriter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.BaseDataWriter`  
**Implements:** `Colossal.OdinSerializer.IDataWriter`, `System.IDisposable`  

## Fields

- `private System.Boolean justStarted`  
- `private System.Boolean forceNoSeparatorNextLine`  
- `private System.Collections.Generic.Dictionary<System.Type, System.Delegate> primitiveTypeWriters`  
- `private System.Collections.Generic.Dictionary<System.Type, System.Int32> seenTypes`  
- `private System.Byte[] buffer`  
- `private System.Int32 bufferIndex`  
- `public System.Boolean FormatAsReadable`  
- `public System.Boolean EnableTypeOptimization`  
- `private static readonly System.UInt32[] ByteToHexCharLookup`  
- `private static readonly System.String NEW_LINE`  

## Constructors

- `public JsonDataWriter()`  
- `public JsonDataWriter(System.IO.Stream stream, Colossal.OdinSerializer.SerializationContext context, System.Boolean formatAsReadable = True)`  

## Methods

- `public virtual BeginArrayNode(System.Int64 length) : System.Void`  
- `public virtual BeginReferenceNode(System.String name, System.Type type, System.Int32 id) : System.Void`  
- `public virtual BeginStructNode(System.String name, System.Type type) : System.Void`  
- `private Buffer_WriteString_WithEscape(System.String str) : System.Void`  
- `private static CreateByteToHexLookup() : System.UInt32[]`  
- `public virtual Dispose() : System.Void`  
- `public virtual EndArrayNode() : System.Void`  
- `public virtual EndNode(System.String name) : System.Void`  
- `private EnsureBufferSpace(System.Int32 space) : System.Void`  
- `public virtual FlushToStream() : System.Void`  
- `public virtual GetDataDump() : System.String`  
- `public MarkJustStarted() : System.Void`  
- `public virtual PrepareNewSerializationSession() : System.Void`  
- `private StartNewLine(System.Boolean noSeparator = False) : System.Void`  
- `public virtual WriteBoolean(System.String name, System.Boolean value) : System.Void`  
- `public virtual WriteByte(System.String name, System.Byte value) : System.Void`  
- `public virtual WriteChar(System.String name, System.Char value) : System.Void`  
- `public virtual WriteDecimal(System.String name, System.Decimal value) : System.Void`  
- `public virtual WriteDouble(System.String name, System.Double value) : System.Void`  
- `private WriteEntry(System.String name, System.String contents) : System.Void`  
- `private WriteEntry(System.String name, System.String contents, System.Char surroundContentsWith) : System.Void`  
- `public virtual WriteExternalReference(System.String name, System.Int32 index) : System.Void`  
- `public virtual WriteExternalReference(System.String name, System.Guid guid) : System.Void`  
- `public virtual WriteExternalReference(System.String name, System.String id) : System.Void`  
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
- `private WriteTypeEntry(System.Type type) : System.Void`  
- `public virtual WriteUInt16(System.String name, System.UInt16 value) : System.Void`  
- `public virtual WriteUInt32(System.String name, System.UInt32 value) : System.Void`  
- `public virtual WriteUInt64(System.String name, System.UInt64 value) : System.Void`  

