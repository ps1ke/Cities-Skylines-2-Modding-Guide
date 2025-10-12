# Colossal.OdinSerializer.BinaryDataReader

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.BaseDataReader`  
**Implements:** `Colossal.OdinSerializer.IDataReader`, `System.IDisposable`  

## Fields

- `private System.Byte[] internalBufferBackup`  
- `private System.Byte[] buffer`  
- `private System.Int32 bufferIndex`  
- `private System.Int32 bufferEnd`  
- `private System.Nullable<Colossal.OdinSerializer.EntryType> peekedEntryType`  
- `private Colossal.OdinSerializer.BinaryEntryType peekedBinaryEntryType`  
- `private System.String peekedEntryName`  
- `private System.Collections.Generic.Dictionary<System.Int32, System.Type> types`  
- `private static readonly System.Collections.Generic.Dictionary<System.Type, System.Delegate> PrimitiveFromByteMethods`  

## Constructors

- `public BinaryDataReader()`  
- `public BinaryDataReader(System.IO.Stream stream, Colossal.OdinSerializer.DeserializationContext context)`  

## Methods

- `public virtual Dispose() : System.Void`  
- `public virtual EnterArray(System.Int64& length) : System.Boolean`  
- `public virtual EnterNode(System.Type& type) : System.Boolean`  
- `public virtual ExitArray() : System.Boolean`  
- `public virtual ExitNode() : System.Boolean`  
- `public virtual GetDataDump() : System.String`  
- `private HasBufferData(System.Int32 amount) : System.Boolean`  
- `private MarkEntryContentConsumed() : System.Void`  
- `public virtual PeekEntry(System.ReadOnlySpan`1[[System.Char, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& name) : Colossal.OdinSerializer.EntryType`  
- `protected virtual PeekEntry() : Colossal.OdinSerializer.EntryType`  
- `public virtual PrepareNewSerializationSession() : System.Void`  
- `public virtual ReadBoolean(System.Boolean& value) : System.Boolean`  
- `public virtual ReadByte(System.Byte& value) : System.Boolean`  
- `public virtual ReadChar(System.Char& value) : System.Boolean`  
- `public virtual ReadDecimal(System.Decimal& value) : System.Boolean`  
- `public virtual ReadDouble(System.Double& value) : System.Boolean`  
- `private ReadEntireStreamToBuffer() : System.Void`  
- `public virtual ReadExternalReference(System.Guid& guid) : System.Boolean`  
- `public virtual ReadExternalReference(System.Int32& index) : System.Boolean`  
- `public virtual ReadExternalReference(System.String& id) : System.Boolean`  
- `public virtual ReadGuid(System.Guid& value) : System.Boolean`  
- `public virtual ReadInt16(System.Int16& value) : System.Boolean`  
- `public virtual ReadInt32(System.Int32& value) : System.Boolean`  
- `public virtual ReadInt64(System.Int64& value) : System.Boolean`  
- `public virtual ReadInternalReference(System.Int32& id) : System.Boolean`  
- `public virtual ReadNull() : System.Boolean`  
- `public virtual ReadPrimitiveArray<T>(T[]& array) : System.Boolean`  
- `public virtual ReadSByte(System.SByte& value) : System.Boolean`  
- `public virtual ReadSingle(System.Single& value) : System.Boolean`  
- `public virtual ReadString(System.String& value) : System.Boolean`  
- `private ReadStringValue() : System.String`  
- `protected virtual ReadToNextEntry() : Colossal.OdinSerializer.EntryType`  
- `private ReadTypeEntry() : System.Type`  
- `public virtual ReadUInt16(System.UInt16& value) : System.Boolean`  
- `public virtual ReadUInt32(System.UInt32& value) : System.Boolean`  
- `public virtual ReadUInt64(System.UInt64& value) : System.Boolean`  
- `private SkipBuffer(System.Int32 amount) : System.Boolean`  
- `private SkipPeekedEntryContent() : System.Void`  
- `private SkipStringValue() : System.Void`  
- `private UNSAFE_Read_1_Byte(System.Byte& value) : System.Boolean`  
- `private UNSAFE_Read_1_SByte(System.SByte& value) : System.Boolean`  
- `private UNSAFE_Read_16_Decimal(System.Decimal& value) : System.Boolean`  
- `private UNSAFE_Read_16_Guid(System.Guid& value) : System.Boolean`  
- `private UNSAFE_Read_2_Char(System.Char& value) : System.Boolean`  
- `private UNSAFE_Read_2_Int16(System.Int16& value) : System.Boolean`  
- `private UNSAFE_Read_2_UInt16(System.UInt16& value) : System.Boolean`  
- `private UNSAFE_Read_4_Float32(System.Single& value) : System.Boolean`  
- `private UNSAFE_Read_4_Int32(System.Int32& value) : System.Boolean`  
- `private UNSAFE_Read_4_UInt32(System.UInt32& value) : System.Boolean`  
- `private UNSAFE_Read_8_Float64(System.Double& value) : System.Boolean`  
- `private UNSAFE_Read_8_Int64(System.Int64& value) : System.Boolean`  
- `private UNSAFE_Read_8_UInt64(System.UInt64& value) : System.Boolean`  

## Nested types

- `Colossal.OdinSerializer.BinaryDataReader+Struct256Bit`  
- `Colossal.OdinSerializer.BinaryDataReader+<>c`  

