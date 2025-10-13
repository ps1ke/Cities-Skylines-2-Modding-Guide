# Colossal.OdinSerializer.BaseDataWriter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class abstract public  

**Base:** `Colossal.OdinSerializer.BaseDataReaderWriter`  
**Implements:** `Colossal.OdinSerializer.IDataWriter`, `System.IDisposable`  

## Code

```csharp
public abstract class BaseDataWriter : Colossal.OdinSerializer.BaseDataReaderWriter, Colossal.OdinSerializer.IDataWriter, System.IDisposable
{
    private Colossal.OdinSerializer.SerializationContext context;
    private System.IO.Stream stream;

    public System.IO.Stream Stream { get; set; }
    public Colossal.OdinSerializer.SerializationContext Context { get; set; }

    protected BaseDataWriter(System.IO.Stream stream, Colossal.OdinSerializer.SerializationContext context);

    public abstract System.Void BeginArrayNode(System.Int64 length);
    public abstract System.Void BeginReferenceNode(System.String name, System.Type type, System.Int32 id);
    public abstract System.Void BeginStructNode(System.String name, System.Type type);
    public abstract System.Void Dispose();
    public abstract System.Void EndArrayNode();
    public abstract System.Void EndNode(System.String name);
    public virtual System.Void FlushToStream();
    public abstract System.String GetDataDump();
    public virtual System.Void PrepareNewSerializationSession();
    public abstract System.Void WriteBoolean(System.String name, System.Boolean value);
    public abstract System.Void WriteByte(System.String name, System.Byte value);
    public abstract System.Void WriteChar(System.String name, System.Char value);
    public abstract System.Void WriteDecimal(System.String name, System.Decimal value);
    public abstract System.Void WriteDouble(System.String name, System.Double value);
    public abstract System.Void WriteExternalReference(System.String name, System.Int32 index);
    public abstract System.Void WriteExternalReference(System.String name, System.Guid guid);
    public abstract System.Void WriteExternalReference(System.String name, System.String id);
    public abstract System.Void WriteGuid(System.String name, System.Guid value);
    public abstract System.Void WriteInt16(System.String name, System.Int16 value);
    public abstract System.Void WriteInt32(System.String name, System.Int32 value);
    public abstract System.Void WriteInt64(System.String name, System.Int64 value);
    public abstract System.Void WriteInternalReference(System.String name, System.Int32 id);
    public abstract System.Void WriteNull(System.String name);
    public abstract System.Void WritePrimitiveArray<T>(T[] array);
    public abstract System.Void WriteSByte(System.String name, System.SByte value);
    public abstract System.Void WriteSingle(System.String name, System.Single value);
    public abstract System.Void WriteString(System.String name, System.String value);
    public abstract System.Void WriteUInt16(System.String name, System.UInt16 value);
    public abstract System.Void WriteUInt32(System.String name, System.UInt32 value);
    public abstract System.Void WriteUInt64(System.String name, System.UInt64 value);
}
```


## Fields

- `private Colossal.OdinSerializer.SerializationContext context`  

```csharp
private Colossal.OdinSerializer.SerializationContext context;
```

- `private System.IO.Stream stream`  

```csharp
private System.IO.Stream stream;
```


## Properties

- `public System.IO.Stream Stream { get; set }`  

```csharp
public System.IO.Stream Stream { get; set; }
```

- `public Colossal.OdinSerializer.SerializationContext Context { get; set }`  

```csharp
public Colossal.OdinSerializer.SerializationContext Context { get; set; }
```


## Constructors

- `protected BaseDataWriter(System.IO.Stream stream, Colossal.OdinSerializer.SerializationContext context)`  

```csharp
protected BaseDataWriter(System.IO.Stream stream, Colossal.OdinSerializer.SerializationContext context);
```


## Methods

- `public abstract BeginArrayNode(System.Int64 length) : System.Void`  

```csharp
public abstract System.Void BeginArrayNode(System.Int64 length);
```

- `public abstract BeginReferenceNode(System.String name, System.Type type, System.Int32 id) : System.Void`  

```csharp
public abstract System.Void BeginReferenceNode(System.String name, System.Type type, System.Int32 id);
```

- `public abstract BeginStructNode(System.String name, System.Type type) : System.Void`  

```csharp
public abstract System.Void BeginStructNode(System.String name, System.Type type);
```

- `public abstract Dispose() : System.Void`  

```csharp
public abstract System.Void Dispose();
```

- `public abstract EndArrayNode() : System.Void`  

```csharp
public abstract System.Void EndArrayNode();
```

- `public abstract EndNode(System.String name) : System.Void`  

```csharp
public abstract System.Void EndNode(System.String name);
```

- `public virtual FlushToStream() : System.Void`  

```csharp
public virtual System.Void FlushToStream();
```

- `public abstract GetDataDump() : System.String`  

```csharp
public abstract System.String GetDataDump();
```

- `public virtual PrepareNewSerializationSession() : System.Void`  

```csharp
public virtual System.Void PrepareNewSerializationSession();
```

- `public abstract WriteBoolean(System.String name, System.Boolean value) : System.Void`  

```csharp
public abstract System.Void WriteBoolean(System.String name, System.Boolean value);
```

- `public abstract WriteByte(System.String name, System.Byte value) : System.Void`  

```csharp
public abstract System.Void WriteByte(System.String name, System.Byte value);
```

- `public abstract WriteChar(System.String name, System.Char value) : System.Void`  

```csharp
public abstract System.Void WriteChar(System.String name, System.Char value);
```

- `public abstract WriteDecimal(System.String name, System.Decimal value) : System.Void`  

```csharp
public abstract System.Void WriteDecimal(System.String name, System.Decimal value);
```

- `public abstract WriteDouble(System.String name, System.Double value) : System.Void`  

```csharp
public abstract System.Void WriteDouble(System.String name, System.Double value);
```

- `public abstract WriteExternalReference(System.String name, System.Int32 index) : System.Void`  

```csharp
public abstract System.Void WriteExternalReference(System.String name, System.Int32 index);
```

- `public abstract WriteExternalReference(System.String name, System.Guid guid) : System.Void`  

```csharp
public abstract System.Void WriteExternalReference(System.String name, System.Guid guid);
```

- `public abstract WriteExternalReference(System.String name, System.String id) : System.Void`  

```csharp
public abstract System.Void WriteExternalReference(System.String name, System.String id);
```

- `public abstract WriteGuid(System.String name, System.Guid value) : System.Void`  

```csharp
public abstract System.Void WriteGuid(System.String name, System.Guid value);
```

- `public abstract WriteInt16(System.String name, System.Int16 value) : System.Void`  

```csharp
public abstract System.Void WriteInt16(System.String name, System.Int16 value);
```

- `public abstract WriteInt32(System.String name, System.Int32 value) : System.Void`  

```csharp
public abstract System.Void WriteInt32(System.String name, System.Int32 value);
```

- `public abstract WriteInt64(System.String name, System.Int64 value) : System.Void`  

```csharp
public abstract System.Void WriteInt64(System.String name, System.Int64 value);
```

- `public abstract WriteInternalReference(System.String name, System.Int32 id) : System.Void`  

```csharp
public abstract System.Void WriteInternalReference(System.String name, System.Int32 id);
```

- `public abstract WriteNull(System.String name) : System.Void`  

```csharp
public abstract System.Void WriteNull(System.String name);
```

- `public abstract WritePrimitiveArray<T>(T[] array) : System.Void`  

```csharp
public abstract System.Void WritePrimitiveArray<T>(T[] array);
```

- `public abstract WriteSByte(System.String name, System.SByte value) : System.Void`  

```csharp
public abstract System.Void WriteSByte(System.String name, System.SByte value);
```

- `public abstract WriteSingle(System.String name, System.Single value) : System.Void`  

```csharp
public abstract System.Void WriteSingle(System.String name, System.Single value);
```

- `public abstract WriteString(System.String name, System.String value) : System.Void`  

```csharp
public abstract System.Void WriteString(System.String name, System.String value);
```

- `public abstract WriteUInt16(System.String name, System.UInt16 value) : System.Void`  

```csharp
public abstract System.Void WriteUInt16(System.String name, System.UInt16 value);
```

- `public abstract WriteUInt32(System.String name, System.UInt32 value) : System.Void`  

```csharp
public abstract System.Void WriteUInt32(System.String name, System.UInt32 value);
```

- `public abstract WriteUInt64(System.String name, System.UInt64 value) : System.Void`  

```csharp
public abstract System.Void WriteUInt64(System.String name, System.UInt64 value);
```


