# Colossal.OdinSerializer.BinaryDataReader

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.BaseDataReader`  
**Implements:** `Colossal.OdinSerializer.IDataReader`, `System.IDisposable`  

## Code

```csharp
public class BinaryDataReader : Colossal.OdinSerializer.BaseDataReader, Colossal.OdinSerializer.IDataReader, System.IDisposable
{
    private System.Byte[] internalBufferBackup;
    private System.Byte[] buffer;
    private System.Int32 bufferIndex;
    private System.Int32 bufferEnd;
    private System.Nullable<Colossal.OdinSerializer.EntryType> peekedEntryType;
    private Colossal.OdinSerializer.BinaryEntryType peekedBinaryEntryType;
    private System.String peekedEntryName;
    private System.Collections.Generic.Dictionary<System.Int32, System.Type> types;
    private static readonly System.Collections.Generic.Dictionary<System.Type, System.Delegate> PrimitiveFromByteMethods;

    public BinaryDataReader();
    public BinaryDataReader(System.IO.Stream stream, Colossal.OdinSerializer.DeserializationContext context);

    public virtual System.Void Dispose();
    public virtual System.Boolean EnterArray(System.Int64& length);
    public virtual System.Boolean EnterNode(System.Type& type);
    public virtual System.Boolean ExitArray();
    public virtual System.Boolean ExitNode();
    public virtual System.String GetDataDump();
    private System.Boolean HasBufferData(System.Int32 amount);
    private System.Void MarkEntryContentConsumed();
    public virtual Colossal.OdinSerializer.EntryType PeekEntry(System.ReadOnlySpan`1[[System.Char, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& name);
    protected virtual Colossal.OdinSerializer.EntryType PeekEntry();
    public virtual System.Void PrepareNewSerializationSession();
    public virtual System.Boolean ReadBoolean(System.Boolean& value);
    public virtual System.Boolean ReadByte(System.Byte& value);
    public virtual System.Boolean ReadChar(System.Char& value);
    public virtual System.Boolean ReadDecimal(System.Decimal& value);
    public virtual System.Boolean ReadDouble(System.Double& value);
    private System.Void ReadEntireStreamToBuffer();
    public virtual System.Boolean ReadExternalReference(System.Guid& guid);
    public virtual System.Boolean ReadExternalReference(System.Int32& index);
    public virtual System.Boolean ReadExternalReference(System.String& id);
    public virtual System.Boolean ReadGuid(System.Guid& value);
    public virtual System.Boolean ReadInt16(System.Int16& value);
    public virtual System.Boolean ReadInt32(System.Int32& value);
    public virtual System.Boolean ReadInt64(System.Int64& value);
    public virtual System.Boolean ReadInternalReference(System.Int32& id);
    public virtual System.Boolean ReadNull();
    public virtual System.Boolean ReadPrimitiveArray<T>(T[]& array);
    public virtual System.Boolean ReadSByte(System.SByte& value);
    public virtual System.Boolean ReadSingle(System.Single& value);
    public virtual System.Boolean ReadString(System.String& value);
    private System.String ReadStringValue();
    protected virtual Colossal.OdinSerializer.EntryType ReadToNextEntry();
    private System.Type ReadTypeEntry();
    public virtual System.Boolean ReadUInt16(System.UInt16& value);
    public virtual System.Boolean ReadUInt32(System.UInt32& value);
    public virtual System.Boolean ReadUInt64(System.UInt64& value);
    private System.Boolean SkipBuffer(System.Int32 amount);
    private System.Void SkipPeekedEntryContent();
    private System.Void SkipStringValue();
    private System.Boolean UNSAFE_Read_1_Byte(System.Byte& value);
    private System.Boolean UNSAFE_Read_1_SByte(System.SByte& value);
    private System.Boolean UNSAFE_Read_16_Decimal(System.Decimal& value);
    private System.Boolean UNSAFE_Read_16_Guid(System.Guid& value);
    private System.Boolean UNSAFE_Read_2_Char(System.Char& value);
    private System.Boolean UNSAFE_Read_2_Int16(System.Int16& value);
    private System.Boolean UNSAFE_Read_2_UInt16(System.UInt16& value);
    private System.Boolean UNSAFE_Read_4_Float32(System.Single& value);
    private System.Boolean UNSAFE_Read_4_Int32(System.Int32& value);
    private System.Boolean UNSAFE_Read_4_UInt32(System.UInt32& value);
    private System.Boolean UNSAFE_Read_8_Float64(System.Double& value);
    private System.Boolean UNSAFE_Read_8_Int64(System.Int64& value);
    private System.Boolean UNSAFE_Read_8_UInt64(System.UInt64& value);
}
```


## Fields

- `private System.Byte[] internalBufferBackup`  

```csharp
private System.Byte[] internalBufferBackup;
```

- `private System.Byte[] buffer`  

```csharp
private System.Byte[] buffer;
```

- `private System.Int32 bufferIndex`  

```csharp
private System.Int32 bufferIndex;
```

- `private System.Int32 bufferEnd`  

```csharp
private System.Int32 bufferEnd;
```

- `private System.Nullable<Colossal.OdinSerializer.EntryType> peekedEntryType`  

```csharp
private System.Nullable<Colossal.OdinSerializer.EntryType> peekedEntryType;
```

- `private Colossal.OdinSerializer.BinaryEntryType peekedBinaryEntryType`  

```csharp
private Colossal.OdinSerializer.BinaryEntryType peekedBinaryEntryType;
```

- `private System.String peekedEntryName`  

```csharp
private System.String peekedEntryName;
```

- `private System.Collections.Generic.Dictionary<System.Int32, System.Type> types`  

```csharp
private System.Collections.Generic.Dictionary<System.Int32, System.Type> types;
```

- `private static readonly System.Collections.Generic.Dictionary<System.Type, System.Delegate> PrimitiveFromByteMethods`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.Type, System.Delegate> PrimitiveFromByteMethods;
```


## Constructors

- `public BinaryDataReader()`  

```csharp
public BinaryDataReader();
```

- `public BinaryDataReader(System.IO.Stream stream, Colossal.OdinSerializer.DeserializationContext context)`  

```csharp
public BinaryDataReader(System.IO.Stream stream, Colossal.OdinSerializer.DeserializationContext context);
```


## Methods

- `public virtual Dispose() : System.Void`  

```csharp
public virtual System.Void Dispose();
```

- `public virtual EnterArray(System.Int64& length) : System.Boolean`  

```csharp
public virtual System.Boolean EnterArray(System.Int64& length);
```

- `public virtual EnterNode(System.Type& type) : System.Boolean`  

```csharp
public virtual System.Boolean EnterNode(System.Type& type);
```

- `public virtual ExitArray() : System.Boolean`  

```csharp
public virtual System.Boolean ExitArray();
```

- `public virtual ExitNode() : System.Boolean`  

```csharp
public virtual System.Boolean ExitNode();
```

- `public virtual GetDataDump() : System.String`  

```csharp
public virtual System.String GetDataDump();
```

- `private HasBufferData(System.Int32 amount) : System.Boolean`  

```csharp
private System.Boolean HasBufferData(System.Int32 amount);
```

- `private MarkEntryContentConsumed() : System.Void`  

```csharp
private System.Void MarkEntryContentConsumed();
```

- `public virtual PeekEntry(System.ReadOnlySpan`1[[System.Char, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& name) : Colossal.OdinSerializer.EntryType`  

```csharp
public virtual Colossal.OdinSerializer.EntryType PeekEntry(System.ReadOnlySpan`1[[System.Char, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& name);
```

- `protected virtual PeekEntry() : Colossal.OdinSerializer.EntryType`  

```csharp
protected virtual Colossal.OdinSerializer.EntryType PeekEntry();
```

- `public virtual PrepareNewSerializationSession() : System.Void`  

```csharp
public virtual System.Void PrepareNewSerializationSession();
```

- `public virtual ReadBoolean(System.Boolean& value) : System.Boolean`  

```csharp
public virtual System.Boolean ReadBoolean(System.Boolean& value);
```

- `public virtual ReadByte(System.Byte& value) : System.Boolean`  

```csharp
public virtual System.Boolean ReadByte(System.Byte& value);
```

- `public virtual ReadChar(System.Char& value) : System.Boolean`  

```csharp
public virtual System.Boolean ReadChar(System.Char& value);
```

- `public virtual ReadDecimal(System.Decimal& value) : System.Boolean`  

```csharp
public virtual System.Boolean ReadDecimal(System.Decimal& value);
```

- `public virtual ReadDouble(System.Double& value) : System.Boolean`  

```csharp
public virtual System.Boolean ReadDouble(System.Double& value);
```

- `private ReadEntireStreamToBuffer() : System.Void`  

```csharp
private System.Void ReadEntireStreamToBuffer();
```

- `public virtual ReadExternalReference(System.Guid& guid) : System.Boolean`  

```csharp
public virtual System.Boolean ReadExternalReference(System.Guid& guid);
```

- `public virtual ReadExternalReference(System.Int32& index) : System.Boolean`  

```csharp
public virtual System.Boolean ReadExternalReference(System.Int32& index);
```

- `public virtual ReadExternalReference(System.String& id) : System.Boolean`  

```csharp
public virtual System.Boolean ReadExternalReference(System.String& id);
```

- `public virtual ReadGuid(System.Guid& value) : System.Boolean`  

```csharp
public virtual System.Boolean ReadGuid(System.Guid& value);
```

- `public virtual ReadInt16(System.Int16& value) : System.Boolean`  

```csharp
public virtual System.Boolean ReadInt16(System.Int16& value);
```

- `public virtual ReadInt32(System.Int32& value) : System.Boolean`  

```csharp
public virtual System.Boolean ReadInt32(System.Int32& value);
```

- `public virtual ReadInt64(System.Int64& value) : System.Boolean`  

```csharp
public virtual System.Boolean ReadInt64(System.Int64& value);
```

- `public virtual ReadInternalReference(System.Int32& id) : System.Boolean`  

```csharp
public virtual System.Boolean ReadInternalReference(System.Int32& id);
```

- `public virtual ReadNull() : System.Boolean`  

```csharp
public virtual System.Boolean ReadNull();
```

- `public virtual ReadPrimitiveArray<T>(T[]& array) : System.Boolean`  

```csharp
public virtual System.Boolean ReadPrimitiveArray<T>(T[]& array);
```

- `public virtual ReadSByte(System.SByte& value) : System.Boolean`  

```csharp
public virtual System.Boolean ReadSByte(System.SByte& value);
```

- `public virtual ReadSingle(System.Single& value) : System.Boolean`  

```csharp
public virtual System.Boolean ReadSingle(System.Single& value);
```

- `public virtual ReadString(System.String& value) : System.Boolean`  

```csharp
public virtual System.Boolean ReadString(System.String& value);
```

- `private ReadStringValue() : System.String`  

```csharp
private System.String ReadStringValue();
```

- `protected virtual ReadToNextEntry() : Colossal.OdinSerializer.EntryType`  

```csharp
protected virtual Colossal.OdinSerializer.EntryType ReadToNextEntry();
```

- `private ReadTypeEntry() : System.Type`  

```csharp
private System.Type ReadTypeEntry();
```

- `public virtual ReadUInt16(System.UInt16& value) : System.Boolean`  

```csharp
public virtual System.Boolean ReadUInt16(System.UInt16& value);
```

- `public virtual ReadUInt32(System.UInt32& value) : System.Boolean`  

```csharp
public virtual System.Boolean ReadUInt32(System.UInt32& value);
```

- `public virtual ReadUInt64(System.UInt64& value) : System.Boolean`  

```csharp
public virtual System.Boolean ReadUInt64(System.UInt64& value);
```

- `private SkipBuffer(System.Int32 amount) : System.Boolean`  

```csharp
private System.Boolean SkipBuffer(System.Int32 amount);
```

- `private SkipPeekedEntryContent() : System.Void`  

```csharp
private System.Void SkipPeekedEntryContent();
```

- `private SkipStringValue() : System.Void`  

```csharp
private System.Void SkipStringValue();
```

- `private UNSAFE_Read_1_Byte(System.Byte& value) : System.Boolean`  

```csharp
private System.Boolean UNSAFE_Read_1_Byte(System.Byte& value);
```

- `private UNSAFE_Read_1_SByte(System.SByte& value) : System.Boolean`  

```csharp
private System.Boolean UNSAFE_Read_1_SByte(System.SByte& value);
```

- `private UNSAFE_Read_16_Decimal(System.Decimal& value) : System.Boolean`  

```csharp
private System.Boolean UNSAFE_Read_16_Decimal(System.Decimal& value);
```

- `private UNSAFE_Read_16_Guid(System.Guid& value) : System.Boolean`  

```csharp
private System.Boolean UNSAFE_Read_16_Guid(System.Guid& value);
```

- `private UNSAFE_Read_2_Char(System.Char& value) : System.Boolean`  

```csharp
private System.Boolean UNSAFE_Read_2_Char(System.Char& value);
```

- `private UNSAFE_Read_2_Int16(System.Int16& value) : System.Boolean`  

```csharp
private System.Boolean UNSAFE_Read_2_Int16(System.Int16& value);
```

- `private UNSAFE_Read_2_UInt16(System.UInt16& value) : System.Boolean`  

```csharp
private System.Boolean UNSAFE_Read_2_UInt16(System.UInt16& value);
```

- `private UNSAFE_Read_4_Float32(System.Single& value) : System.Boolean`  

```csharp
private System.Boolean UNSAFE_Read_4_Float32(System.Single& value);
```

- `private UNSAFE_Read_4_Int32(System.Int32& value) : System.Boolean`  

```csharp
private System.Boolean UNSAFE_Read_4_Int32(System.Int32& value);
```

- `private UNSAFE_Read_4_UInt32(System.UInt32& value) : System.Boolean`  

```csharp
private System.Boolean UNSAFE_Read_4_UInt32(System.UInt32& value);
```

- `private UNSAFE_Read_8_Float64(System.Double& value) : System.Boolean`  

```csharp
private System.Boolean UNSAFE_Read_8_Float64(System.Double& value);
```

- `private UNSAFE_Read_8_Int64(System.Int64& value) : System.Boolean`  

```csharp
private System.Boolean UNSAFE_Read_8_Int64(System.Int64& value);
```

- `private UNSAFE_Read_8_UInt64(System.UInt64& value) : System.Boolean`  

```csharp
private System.Boolean UNSAFE_Read_8_UInt64(System.UInt64& value);
```


## Nested types

- `Colossal.OdinSerializer.BinaryDataReader+Struct256Bit`  
- `Colossal.OdinSerializer.BinaryDataReader+<>c`  

