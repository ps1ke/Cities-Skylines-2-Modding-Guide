# Colossal.OdinSerializer.SerializationNodeDataReader

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.BaseDataReader`  
**Implements:** `Colossal.OdinSerializer.IDataReader`, `System.IDisposable`  

## Code

```csharp
public class SerializationNodeDataReader : Colossal.OdinSerializer.BaseDataReader, Colossal.OdinSerializer.IDataReader, System.IDisposable
{
    private System.String peekedEntryName;
    private System.Nullable<Colossal.OdinSerializer.EntryType> peekedEntryType;
    private System.String peekedEntryData;
    private System.Int32 currentIndex;
    private System.Collections.Generic.List<Colossal.OdinSerializer.SerializationNode> nodes;
    private System.Collections.Generic.Dictionary<System.Type, System.Delegate> primitiveTypeReaders;

    private System.Boolean IndexIsValid { private get; }
    public System.Collections.Generic.List<Colossal.OdinSerializer.SerializationNode> Nodes { get; set; }
    public System.IO.Stream Stream { get; set; }

    public SerializationNodeDataReader(Colossal.OdinSerializer.DeserializationContext context);

    private System.Char <.ctor>b__6_0();
    private System.SByte <.ctor>b__6_1();
    private System.Boolean <.ctor>b__6_10();
    private System.Single <.ctor>b__6_11();
    private System.Double <.ctor>b__6_12();
    private System.Guid <.ctor>b__6_13();
    private System.Int16 <.ctor>b__6_2();
    private System.Int32 <.ctor>b__6_3();
    private System.Int64 <.ctor>b__6_4();
    private System.Byte <.ctor>b__6_5();
    private System.UInt16 <.ctor>b__6_6();
    private System.UInt32 <.ctor>b__6_7();
    private System.UInt64 <.ctor>b__6_8();
    private System.Decimal <.ctor>b__6_9();
    private System.Void ConsumeCurrentEntry();
    public virtual System.Void Dispose();
    public virtual System.Boolean EnterArray(System.Int64& length);
    public virtual System.Boolean EnterNode(System.Type& type);
    public virtual System.Boolean ExitArray();
    public virtual System.Boolean ExitNode();
    public virtual System.String GetDataDump();
    public virtual Colossal.OdinSerializer.EntryType PeekEntry(System.ReadOnlySpan`1[[System.Char, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& name);
    protected virtual Colossal.OdinSerializer.EntryType PeekEntry();
    public virtual System.Void PrepareNewSerializationSession();
    public virtual System.Boolean ReadBoolean(System.Boolean& value);
    public virtual System.Boolean ReadByte(System.Byte& value);
    public virtual System.Boolean ReadChar(System.Char& value);
    public virtual System.Boolean ReadDecimal(System.Decimal& value);
    public virtual System.Boolean ReadDouble(System.Double& value);
    public virtual System.Boolean ReadExternalReference(System.Guid& guid);
    public virtual System.Boolean ReadExternalReference(System.String& id);
    public virtual System.Boolean ReadExternalReference(System.Int32& index);
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
    protected virtual Colossal.OdinSerializer.EntryType ReadToNextEntry();
    public virtual System.Boolean ReadUInt16(System.UInt16& value);
    public virtual System.Boolean ReadUInt32(System.UInt32& value);
    public virtual System.Boolean ReadUInt64(System.UInt64& value);
}
```


## Fields

- `private System.String peekedEntryName`  

```csharp
private System.String peekedEntryName;
```

- `private System.Nullable<Colossal.OdinSerializer.EntryType> peekedEntryType`  

```csharp
private System.Nullable<Colossal.OdinSerializer.EntryType> peekedEntryType;
```

- `private System.String peekedEntryData`  

```csharp
private System.String peekedEntryData;
```

- `private System.Int32 currentIndex`  

```csharp
private System.Int32 currentIndex;
```

- `private System.Collections.Generic.List<Colossal.OdinSerializer.SerializationNode> nodes`  

```csharp
private System.Collections.Generic.List<Colossal.OdinSerializer.SerializationNode> nodes;
```

- `private System.Collections.Generic.Dictionary<System.Type, System.Delegate> primitiveTypeReaders`  

```csharp
private System.Collections.Generic.Dictionary<System.Type, System.Delegate> primitiveTypeReaders;
```


## Properties

- `private System.Boolean IndexIsValid { private get }`  

```csharp
private System.Boolean IndexIsValid { private get; }
```

- `public System.Collections.Generic.List<Colossal.OdinSerializer.SerializationNode> Nodes { get; set }`  

```csharp
public System.Collections.Generic.List<Colossal.OdinSerializer.SerializationNode> Nodes { get; set; }
```

- `public System.IO.Stream Stream { get; set }`  

```csharp
public System.IO.Stream Stream { get; set; }
```


## Constructors

- `public SerializationNodeDataReader(Colossal.OdinSerializer.DeserializationContext context)`  

```csharp
public SerializationNodeDataReader(Colossal.OdinSerializer.DeserializationContext context);
```


## Methods

- `private <.ctor>b__6_0() : System.Char`  

```csharp
private System.Char <.ctor>b__6_0();
```

- `private <.ctor>b__6_1() : System.SByte`  

```csharp
private System.SByte <.ctor>b__6_1();
```

- `private <.ctor>b__6_10() : System.Boolean`  

```csharp
private System.Boolean <.ctor>b__6_10();
```

- `private <.ctor>b__6_11() : System.Single`  

```csharp
private System.Single <.ctor>b__6_11();
```

- `private <.ctor>b__6_12() : System.Double`  

```csharp
private System.Double <.ctor>b__6_12();
```

- `private <.ctor>b__6_13() : System.Guid`  

```csharp
private System.Guid <.ctor>b__6_13();
```

- `private <.ctor>b__6_2() : System.Int16`  

```csharp
private System.Int16 <.ctor>b__6_2();
```

- `private <.ctor>b__6_3() : System.Int32`  

```csharp
private System.Int32 <.ctor>b__6_3();
```

- `private <.ctor>b__6_4() : System.Int64`  

```csharp
private System.Int64 <.ctor>b__6_4();
```

- `private <.ctor>b__6_5() : System.Byte`  

```csharp
private System.Byte <.ctor>b__6_5();
```

- `private <.ctor>b__6_6() : System.UInt16`  

```csharp
private System.UInt16 <.ctor>b__6_6();
```

- `private <.ctor>b__6_7() : System.UInt32`  

```csharp
private System.UInt32 <.ctor>b__6_7();
```

- `private <.ctor>b__6_8() : System.UInt64`  

```csharp
private System.UInt64 <.ctor>b__6_8();
```

- `private <.ctor>b__6_9() : System.Decimal`  

```csharp
private System.Decimal <.ctor>b__6_9();
```

- `private ConsumeCurrentEntry() : System.Void`  

```csharp
private System.Void ConsumeCurrentEntry();
```

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

- `public virtual ReadExternalReference(System.Guid& guid) : System.Boolean`  

```csharp
public virtual System.Boolean ReadExternalReference(System.Guid& guid);
```

- `public virtual ReadExternalReference(System.String& id) : System.Boolean`  

```csharp
public virtual System.Boolean ReadExternalReference(System.String& id);
```

- `public virtual ReadExternalReference(System.Int32& index) : System.Boolean`  

```csharp
public virtual System.Boolean ReadExternalReference(System.Int32& index);
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

- `protected virtual ReadToNextEntry() : Colossal.OdinSerializer.EntryType`  

```csharp
protected virtual Colossal.OdinSerializer.EntryType ReadToNextEntry();
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


