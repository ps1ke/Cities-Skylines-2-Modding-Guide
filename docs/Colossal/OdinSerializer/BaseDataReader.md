# Colossal.OdinSerializer.BaseDataReader

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class abstract public  

**Base:** `Colossal.OdinSerializer.BaseDataReaderWriter`  
**Implements:** `Colossal.OdinSerializer.IDataReader`, `System.IDisposable`  

## Fields

- `private Colossal.OdinSerializer.DeserializationContext context`  
- `private System.IO.Stream stream`  

## Properties

- `public System.Int32 CurrentNodeId { get }`  
- `public System.Int32 CurrentNodeDepth { get }`  
- `public System.String CurrentNodeName { get }`  
- `public System.IO.Stream Stream { get; set }`  
- `public Colossal.OdinSerializer.DeserializationContext Context { get; set }`  

## Constructors

- `protected BaseDataReader(System.IO.Stream stream, Colossal.OdinSerializer.DeserializationContext context)`  

## Methods

- `public abstract Dispose() : System.Void`  
- `public abstract EnterArray(System.Int64& length) : System.Boolean`  
- `public abstract EnterNode(System.Type& type) : System.Boolean`  
- `public abstract ExitArray() : System.Boolean`  
- `public abstract ExitNode() : System.Boolean`  
- `public abstract GetDataDump() : System.String`  
- `public abstract PeekEntry(System.ReadOnlySpan`1[[System.Char, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& name) : Colossal.OdinSerializer.EntryType`  
- `protected abstract PeekEntry() : Colossal.OdinSerializer.EntryType`  
- `public virtual PrepareNewSerializationSession() : System.Void`  
- `public abstract ReadBoolean(System.Boolean& value) : System.Boolean`  
- `public abstract ReadByte(System.Byte& value) : System.Boolean`  
- `public abstract ReadChar(System.Char& value) : System.Boolean`  
- `public abstract ReadDecimal(System.Decimal& value) : System.Boolean`  
- `public abstract ReadDouble(System.Double& value) : System.Boolean`  
- `public abstract ReadExternalReference(System.Int32& index) : System.Boolean`  
- `public abstract ReadExternalReference(System.Guid& guid) : System.Boolean`  
- `public abstract ReadExternalReference(System.String& id) : System.Boolean`  
- `public abstract ReadGuid(System.Guid& value) : System.Boolean`  
- `public abstract ReadInt16(System.Int16& value) : System.Boolean`  
- `public abstract ReadInt32(System.Int32& value) : System.Boolean`  
- `public abstract ReadInt64(System.Int64& value) : System.Boolean`  
- `public abstract ReadInternalReference(System.Int32& id) : System.Boolean`  
- `public abstract ReadNull() : System.Boolean`  
- `public abstract ReadPrimitiveArray<T>(T[]& array) : System.Boolean`  
- `public abstract ReadSByte(System.SByte& value) : System.Boolean`  
- `public abstract ReadSingle(System.Single& value) : System.Boolean`  
- `public abstract ReadString(System.String& value) : System.Boolean`  
- `protected abstract ReadToNextEntry() : Colossal.OdinSerializer.EntryType`  
- `public abstract ReadUInt16(System.UInt16& value) : System.Boolean`  
- `public abstract ReadUInt32(System.UInt32& value) : System.Boolean`  
- `public abstract ReadUInt64(System.UInt64& value) : System.Boolean`  
- `public virtual SkipEntry() : System.Void`  

