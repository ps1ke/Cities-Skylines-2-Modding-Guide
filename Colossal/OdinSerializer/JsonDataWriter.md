# Colossal.OdinSerializer.JsonDataWriter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.BaseDataWriter`  
**Implements:** `Colossal.OdinSerializer.IDataWriter`, `System.IDisposable`  

## Code

```csharp
public class JsonDataWriter : Colossal.OdinSerializer.BaseDataWriter, Colossal.OdinSerializer.IDataWriter, System.IDisposable
{
    private System.Boolean justStarted;
    private System.Boolean forceNoSeparatorNextLine;
    private System.Collections.Generic.Dictionary<System.Type, System.Delegate> primitiveTypeWriters;
    private System.Collections.Generic.Dictionary<System.Type, System.Int32> seenTypes;
    private System.Byte[] buffer;
    private System.Int32 bufferIndex;
    public System.Boolean FormatAsReadable;
    public System.Boolean EnableTypeOptimization;
    private static readonly System.UInt32[] ByteToHexCharLookup;
    private static readonly System.String NEW_LINE;

    public JsonDataWriter();
    public JsonDataWriter(System.IO.Stream stream, Colossal.OdinSerializer.SerializationContext context, System.Boolean formatAsReadable);

    public virtual System.Void BeginArrayNode(System.Int64 length);
    public virtual System.Void BeginReferenceNode(System.String name, System.Type type, System.Int32 id);
    public virtual System.Void BeginStructNode(System.String name, System.Type type);
    private System.Void Buffer_WriteString_WithEscape(System.String str);
    private static System.UInt32[] CreateByteToHexLookup();
    public virtual System.Void Dispose();
    public virtual System.Void EndArrayNode();
    public virtual System.Void EndNode(System.String name);
    private System.Void EnsureBufferSpace(System.Int32 space);
    public virtual System.Void FlushToStream();
    public virtual System.String GetDataDump();
    public System.Void MarkJustStarted();
    public virtual System.Void PrepareNewSerializationSession();
    private System.Void StartNewLine(System.Boolean noSeparator);
    public virtual System.Void WriteBoolean(System.String name, System.Boolean value);
    public virtual System.Void WriteByte(System.String name, System.Byte value);
    public virtual System.Void WriteChar(System.String name, System.Char value);
    public virtual System.Void WriteDecimal(System.String name, System.Decimal value);
    public virtual System.Void WriteDouble(System.String name, System.Double value);
    private System.Void WriteEntry(System.String name, System.String contents);
    private System.Void WriteEntry(System.String name, System.String contents, System.Char surroundContentsWith);
    public virtual System.Void WriteExternalReference(System.String name, System.Int32 index);
    public virtual System.Void WriteExternalReference(System.String name, System.Guid guid);
    public virtual System.Void WriteExternalReference(System.String name, System.String id);
    public virtual System.Void WriteGuid(System.String name, System.Guid value);
    public virtual System.Void WriteInt16(System.String name, System.Int16 value);
    public virtual System.Void WriteInt32(System.String name, System.Int32 value);
    public virtual System.Void WriteInt64(System.String name, System.Int64 value);
    public virtual System.Void WriteInternalReference(System.String name, System.Int32 id);
    public virtual System.Void WriteNull(System.String name);
    public virtual System.Void WritePrimitiveArray<T>(T[] array);
    public virtual System.Void WriteSByte(System.String name, System.SByte value);
    public virtual System.Void WriteSingle(System.String name, System.Single value);
    public virtual System.Void WriteString(System.String name, System.String value);
    private System.Void WriteTypeEntry(System.Type type);
    public virtual System.Void WriteUInt16(System.String name, System.UInt16 value);
    public virtual System.Void WriteUInt32(System.String name, System.UInt32 value);
    public virtual System.Void WriteUInt64(System.String name, System.UInt64 value);
}
```


## Fields

- `private System.Boolean justStarted`  

```csharp
private System.Boolean justStarted;
```

- `private System.Boolean forceNoSeparatorNextLine`  

```csharp
private System.Boolean forceNoSeparatorNextLine;
```

- `private System.Collections.Generic.Dictionary<System.Type, System.Delegate> primitiveTypeWriters`  

```csharp
private System.Collections.Generic.Dictionary<System.Type, System.Delegate> primitiveTypeWriters;
```

- `private System.Collections.Generic.Dictionary<System.Type, System.Int32> seenTypes`  

```csharp
private System.Collections.Generic.Dictionary<System.Type, System.Int32> seenTypes;
```

- `private System.Byte[] buffer`  

```csharp
private System.Byte[] buffer;
```

- `private System.Int32 bufferIndex`  

```csharp
private System.Int32 bufferIndex;
```

- `public System.Boolean FormatAsReadable`  

```csharp
public System.Boolean FormatAsReadable;
```

- `public System.Boolean EnableTypeOptimization`  

```csharp
public System.Boolean EnableTypeOptimization;
```

- `private static readonly System.UInt32[] ByteToHexCharLookup`  

```csharp
private static readonly System.UInt32[] ByteToHexCharLookup;
```

- `private static readonly System.String NEW_LINE`  

```csharp
private static readonly System.String NEW_LINE;
```


## Constructors

- `public JsonDataWriter()`  

```csharp
public JsonDataWriter();
```

- `public JsonDataWriter(System.IO.Stream stream, Colossal.OdinSerializer.SerializationContext context, System.Boolean formatAsReadable = True)`  

```csharp
public JsonDataWriter(System.IO.Stream stream, Colossal.OdinSerializer.SerializationContext context, System.Boolean formatAsReadable);
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

- `private Buffer_WriteString_WithEscape(System.String str) : System.Void`  

```csharp
private System.Void Buffer_WriteString_WithEscape(System.String str);
```

- `private static CreateByteToHexLookup() : System.UInt32[]`  

```csharp
private static System.UInt32[] CreateByteToHexLookup();
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

- `public MarkJustStarted() : System.Void`  

```csharp
public System.Void MarkJustStarted();
```

- `public virtual PrepareNewSerializationSession() : System.Void`  

```csharp
public virtual System.Void PrepareNewSerializationSession();
```

- `private StartNewLine(System.Boolean noSeparator = False) : System.Void`  

```csharp
private System.Void StartNewLine(System.Boolean noSeparator);
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

- `private WriteEntry(System.String name, System.String contents) : System.Void`  

```csharp
private System.Void WriteEntry(System.String name, System.String contents);
```

- `private WriteEntry(System.String name, System.String contents, System.Char surroundContentsWith) : System.Void`  

```csharp
private System.Void WriteEntry(System.String name, System.String contents, System.Char surroundContentsWith);
```

- `public virtual WriteExternalReference(System.String name, System.Int32 index) : System.Void`  

```csharp
public virtual System.Void WriteExternalReference(System.String name, System.Int32 index);
```

- `public virtual WriteExternalReference(System.String name, System.Guid guid) : System.Void`  

```csharp
public virtual System.Void WriteExternalReference(System.String name, System.Guid guid);
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

- `private WriteTypeEntry(System.Type type) : System.Void`  

```csharp
private System.Void WriteTypeEntry(System.Type type);
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


