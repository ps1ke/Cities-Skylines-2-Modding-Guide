# Colossal.OdinSerializer.IDataReader

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** interface abstract public  

**Implements:** `System.IDisposable`  

## Properties

- `public Colossal.OdinSerializer.TwoWaySerializationBinder Binder { get; set }`  
- `public System.IO.Stream Stream { get; set }`  
- `public System.Boolean IsInArrayNode { get }`  
- `public System.String CurrentNodeName { get }`  
- `public System.Int32 CurrentNodeId { get }`  
- `public System.Int32 CurrentNodeDepth { get }`  
- `public Colossal.OdinSerializer.DeserializationContext Context { get; set }`  

## Methods

- `public abstract EnterArray(System.Int64& length) : System.Boolean`  
- `public abstract EnterNode(System.Type& type) : System.Boolean`  
- `public abstract ExitArray() : System.Boolean`  
- `public abstract ExitNode() : System.Boolean`  
- `public abstract GetDataDump() : System.String`  
- `public abstract PeekEntry(System.ReadOnlySpan`1[[System.Char, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& name) : Colossal.OdinSerializer.EntryType`  
- `public abstract PrepareNewSerializationSession() : System.Void`  
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
- `public abstract ReadUInt16(System.UInt16& value) : System.Boolean`  
- `public abstract ReadUInt32(System.UInt32& value) : System.Boolean`  
- `public abstract ReadUInt64(System.UInt64& value) : System.Boolean`  
- `public abstract SkipEntry() : System.Void`  

