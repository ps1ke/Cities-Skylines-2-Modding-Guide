# Colossal.OdinSerializer.BaseDataReader

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class abstract public  

**Base:** `Colossal.OdinSerializer.BaseDataReaderWriter`  
**Implements:** `Colossal.OdinSerializer.IDataReader`, `System.IDisposable`  

## Code

```csharp
public abstract class BaseDataReader : Colossal.OdinSerializer.BaseDataReaderWriter, Colossal.OdinSerializer.IDataReader, System.IDisposable
{
    private Colossal.OdinSerializer.DeserializationContext context;
    private System.IO.Stream stream;

    public System.Int32 CurrentNodeId { get; }
    public System.Int32 CurrentNodeDepth { get; }
    public System.String CurrentNodeName { get; }
    public System.IO.Stream Stream { get; set; }
    public Colossal.OdinSerializer.DeserializationContext Context { get; set; }

    protected BaseDataReader(System.IO.Stream stream, Colossal.OdinSerializer.DeserializationContext context);

    public abstract System.Void Dispose();
    public abstract System.Boolean EnterArray(System.Int64& length);
    public abstract System.Boolean EnterNode(System.Type& type);
    public abstract System.Boolean ExitArray();
    public abstract System.Boolean ExitNode();
    public abstract System.String GetDataDump();
    public abstract Colossal.OdinSerializer.EntryType PeekEntry(System.ReadOnlySpan`1[[System.Char, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& name);
    protected abstract Colossal.OdinSerializer.EntryType PeekEntry();
    public virtual System.Void PrepareNewSerializationSession();
    public abstract System.Boolean ReadBoolean(System.Boolean& value);
    public abstract System.Boolean ReadByte(System.Byte& value);
    public abstract System.Boolean ReadChar(System.Char& value);
    public abstract System.Boolean ReadDecimal(System.Decimal& value);
    public abstract System.Boolean ReadDouble(System.Double& value);
    public abstract System.Boolean ReadExternalReference(System.Int32& index);
    public abstract System.Boolean ReadExternalReference(System.Guid& guid);
    public abstract System.Boolean ReadExternalReference(System.String& id);
    public abstract System.Boolean ReadGuid(System.Guid& value);
    public abstract System.Boolean ReadInt16(System.Int16& value);
    public abstract System.Boolean ReadInt32(System.Int32& value);
    public abstract System.Boolean ReadInt64(System.Int64& value);
    public abstract System.Boolean ReadInternalReference(System.Int32& id);
    public abstract System.Boolean ReadNull();
    public abstract System.Boolean ReadPrimitiveArray<T>(T[]& array);
    public abstract System.Boolean ReadSByte(System.SByte& value);
    public abstract System.Boolean ReadSingle(System.Single& value);
    public abstract System.Boolean ReadString(System.String& value);
    protected abstract Colossal.OdinSerializer.EntryType ReadToNextEntry();
    public abstract System.Boolean ReadUInt16(System.UInt16& value);
    public abstract System.Boolean ReadUInt32(System.UInt32& value);
    public abstract System.Boolean ReadUInt64(System.UInt64& value);
    public virtual System.Void SkipEntry();
}
```


## Fields

- `private Colossal.OdinSerializer.DeserializationContext context`  

```csharp
private Colossal.OdinSerializer.DeserializationContext context;
```

- `private System.IO.Stream stream`  

```csharp
private System.IO.Stream stream;
```


## Properties

- `public System.Int32 CurrentNodeId { get }`  

```csharp
public System.Int32 CurrentNodeId { get; }
```

- `public System.Int32 CurrentNodeDepth { get }`  

```csharp
public System.Int32 CurrentNodeDepth { get; }
```

- `public System.String CurrentNodeName { get }`  

```csharp
public System.String CurrentNodeName { get; }
```

- `public System.IO.Stream Stream { get; set }`  

```csharp
public System.IO.Stream Stream { get; set; }
```

- `public Colossal.OdinSerializer.DeserializationContext Context { get; set }`  

```csharp
public Colossal.OdinSerializer.DeserializationContext Context { get; set; }
```


## Constructors

- `protected BaseDataReader(System.IO.Stream stream, Colossal.OdinSerializer.DeserializationContext context)`  

```csharp
protected BaseDataReader(System.IO.Stream stream, Colossal.OdinSerializer.DeserializationContext context);
```


## Methods

- `public abstract Dispose() : System.Void`  

```csharp
public abstract System.Void Dispose();
```

- `public abstract EnterArray(System.Int64& length) : System.Boolean`  

```csharp
public abstract System.Boolean EnterArray(System.Int64& length);
```

- `public abstract EnterNode(System.Type& type) : System.Boolean`  

```csharp
public abstract System.Boolean EnterNode(System.Type& type);
```

- `public abstract ExitArray() : System.Boolean`  

```csharp
public abstract System.Boolean ExitArray();
```

- `public abstract ExitNode() : System.Boolean`  

```csharp
public abstract System.Boolean ExitNode();
```

- `public abstract GetDataDump() : System.String`  

```csharp
public abstract System.String GetDataDump();
```

- `public abstract PeekEntry(System.ReadOnlySpan`1[[System.Char, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& name) : Colossal.OdinSerializer.EntryType`  

```csharp
public abstract Colossal.OdinSerializer.EntryType PeekEntry(System.ReadOnlySpan`1[[System.Char, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& name);
```

- `protected abstract PeekEntry() : Colossal.OdinSerializer.EntryType`  

```csharp
protected abstract Colossal.OdinSerializer.EntryType PeekEntry();
```

- `public virtual PrepareNewSerializationSession() : System.Void`  

```csharp
public virtual System.Void PrepareNewSerializationSession();
```

- `public abstract ReadBoolean(System.Boolean& value) : System.Boolean`  

```csharp
public abstract System.Boolean ReadBoolean(System.Boolean& value);
```

- `public abstract ReadByte(System.Byte& value) : System.Boolean`  

```csharp
public abstract System.Boolean ReadByte(System.Byte& value);
```

- `public abstract ReadChar(System.Char& value) : System.Boolean`  

```csharp
public abstract System.Boolean ReadChar(System.Char& value);
```

- `public abstract ReadDecimal(System.Decimal& value) : System.Boolean`  

```csharp
public abstract System.Boolean ReadDecimal(System.Decimal& value);
```

- `public abstract ReadDouble(System.Double& value) : System.Boolean`  

```csharp
public abstract System.Boolean ReadDouble(System.Double& value);
```

- `public abstract ReadExternalReference(System.Int32& index) : System.Boolean`  

```csharp
public abstract System.Boolean ReadExternalReference(System.Int32& index);
```

- `public abstract ReadExternalReference(System.Guid& guid) : System.Boolean`  

```csharp
public abstract System.Boolean ReadExternalReference(System.Guid& guid);
```

- `public abstract ReadExternalReference(System.String& id) : System.Boolean`  

```csharp
public abstract System.Boolean ReadExternalReference(System.String& id);
```

- `public abstract ReadGuid(System.Guid& value) : System.Boolean`  

```csharp
public abstract System.Boolean ReadGuid(System.Guid& value);
```

- `public abstract ReadInt16(System.Int16& value) : System.Boolean`  

```csharp
public abstract System.Boolean ReadInt16(System.Int16& value);
```

- `public abstract ReadInt32(System.Int32& value) : System.Boolean`  

```csharp
public abstract System.Boolean ReadInt32(System.Int32& value);
```

- `public abstract ReadInt64(System.Int64& value) : System.Boolean`  

```csharp
public abstract System.Boolean ReadInt64(System.Int64& value);
```

- `public abstract ReadInternalReference(System.Int32& id) : System.Boolean`  

```csharp
public abstract System.Boolean ReadInternalReference(System.Int32& id);
```

- `public abstract ReadNull() : System.Boolean`  

```csharp
public abstract System.Boolean ReadNull();
```

- `public abstract ReadPrimitiveArray<T>(T[]& array) : System.Boolean`  

```csharp
public abstract System.Boolean ReadPrimitiveArray<T>(T[]& array);
```

- `public abstract ReadSByte(System.SByte& value) : System.Boolean`  

```csharp
public abstract System.Boolean ReadSByte(System.SByte& value);
```

- `public abstract ReadSingle(System.Single& value) : System.Boolean`  

```csharp
public abstract System.Boolean ReadSingle(System.Single& value);
```

- `public abstract ReadString(System.String& value) : System.Boolean`  

```csharp
public abstract System.Boolean ReadString(System.String& value);
```

- `protected abstract ReadToNextEntry() : Colossal.OdinSerializer.EntryType`  

```csharp
protected abstract Colossal.OdinSerializer.EntryType ReadToNextEntry();
```

- `public abstract ReadUInt16(System.UInt16& value) : System.Boolean`  

```csharp
public abstract System.Boolean ReadUInt16(System.UInt16& value);
```

- `public abstract ReadUInt32(System.UInt32& value) : System.Boolean`  

```csharp
public abstract System.Boolean ReadUInt32(System.UInt32& value);
```

- `public abstract ReadUInt64(System.UInt64& value) : System.Boolean`  

```csharp
public abstract System.Boolean ReadUInt64(System.UInt64& value);
```

- `public virtual SkipEntry() : System.Void`  

```csharp
public virtual System.Void SkipEntry();
```


