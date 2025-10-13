# Colossal.OdinSerializer.SerializationNodeDataWriter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.BaseDataWriter`  
**Implements:** `Colossal.OdinSerializer.IDataWriter`, `System.IDisposable`  

## Code

```csharp
public class SerializationNodeDataWriter : Colossal.OdinSerializer.BaseDataWriter, Colossal.OdinSerializer.IDataWriter, System.IDisposable
{
    private System.Collections.Generic.List<Colossal.OdinSerializer.SerializationNode> nodes;
    private System.Collections.Generic.Dictionary<System.Type, System.Delegate> primitiveTypeWriters;

    public System.Collections.Generic.List<Colossal.OdinSerializer.SerializationNode> Nodes { get; set; }
    public System.IO.Stream Stream { get; set; }

    public SerializationNodeDataWriter(Colossal.OdinSerializer.SerializationContext context);

    public virtual System.Void BeginArrayNode(System.Int64 length);
    public virtual System.Void BeginReferenceNode(System.String name, System.Type type, System.Int32 id);
    public virtual System.Void BeginStructNode(System.String name, System.Type type);
    public virtual System.Void Dispose();
    public virtual System.Void EndArrayNode();
    public virtual System.Void EndNode(System.String name);
    public virtual System.Void FlushToStream();
    public virtual System.String GetDataDump();
    public virtual System.Void PrepareNewSerializationSession();
    public virtual System.Void WriteBoolean(System.String name, System.Boolean value);
    public virtual System.Void WriteByte(System.String name, System.Byte value);
    public virtual System.Void WriteChar(System.String name, System.Char value);
    public virtual System.Void WriteDecimal(System.String name, System.Decimal value);
    public virtual System.Void WriteDouble(System.String name, System.Double value);
    public virtual System.Void WriteExternalReference(System.String name, System.Guid guid);
    public virtual System.Void WriteExternalReference(System.String name, System.String id);
    public virtual System.Void WriteExternalReference(System.String name, System.Int32 index);
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
    public virtual System.Void WriteUInt16(System.String name, System.UInt16 value);
    public virtual System.Void WriteUInt32(System.String name, System.UInt32 value);
    public virtual System.Void WriteUInt64(System.String name, System.UInt64 value);
}
```


## Fields

- `private System.Collections.Generic.List<Colossal.OdinSerializer.SerializationNode> nodes`  

```csharp
private System.Collections.Generic.List<Colossal.OdinSerializer.SerializationNode> nodes;
```

- `private System.Collections.Generic.Dictionary<System.Type, System.Delegate> primitiveTypeWriters`  

```csharp
private System.Collections.Generic.Dictionary<System.Type, System.Delegate> primitiveTypeWriters;
```


## Properties

- `public System.Collections.Generic.List<Colossal.OdinSerializer.SerializationNode> Nodes { get; set }`  

```csharp
public System.Collections.Generic.List<Colossal.OdinSerializer.SerializationNode> Nodes { get; set; }
```

- `public System.IO.Stream Stream { get; set }`  

```csharp
public System.IO.Stream Stream { get; set; }
```


## Constructors

- `public SerializationNodeDataWriter(Colossal.OdinSerializer.SerializationContext context)`  

```csharp
public SerializationNodeDataWriter(Colossal.OdinSerializer.SerializationContext context);
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

- `public virtual WriteExternalReference(System.String name, System.String id) : System.Void`  

```csharp
public virtual System.Void WriteExternalReference(System.String name, System.String id);
```

- `public virtual WriteExternalReference(System.String name, System.Int32 index) : System.Void`  

```csharp
public virtual System.Void WriteExternalReference(System.String name, System.Int32 index);
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


