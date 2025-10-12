# Colossal.OdinSerializer.SerializationNodeDataReader

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.BaseDataReader`  
**Implements:** `Colossal.OdinSerializer.IDataReader`, `System.IDisposable`  

## Fields

- `private System.String peekedEntryName`  
- `private System.Nullable<Colossal.OdinSerializer.EntryType> peekedEntryType`  
- `private System.String peekedEntryData`  
- `private System.Int32 currentIndex`  
- `private System.Collections.Generic.List<Colossal.OdinSerializer.SerializationNode> nodes`  
- `private System.Collections.Generic.Dictionary<System.Type, System.Delegate> primitiveTypeReaders`  

## Properties

- `private System.Boolean IndexIsValid { private get }`  
- `public System.Collections.Generic.List<Colossal.OdinSerializer.SerializationNode> Nodes { get; set }`  
- `public System.IO.Stream Stream { get; set }`  

## Constructors

- `public SerializationNodeDataReader(Colossal.OdinSerializer.DeserializationContext context)`  

## Methods

- `private <.ctor>b__6_0() : System.Char`  
- `private <.ctor>b__6_1() : System.SByte`  
- `private <.ctor>b__6_10() : System.Boolean`  
- `private <.ctor>b__6_11() : System.Single`  
- `private <.ctor>b__6_12() : System.Double`  
- `private <.ctor>b__6_13() : System.Guid`  
- `private <.ctor>b__6_2() : System.Int16`  
- `private <.ctor>b__6_3() : System.Int32`  
- `private <.ctor>b__6_4() : System.Int64`  
- `private <.ctor>b__6_5() : System.Byte`  
- `private <.ctor>b__6_6() : System.UInt16`  
- `private <.ctor>b__6_7() : System.UInt32`  
- `private <.ctor>b__6_8() : System.UInt64`  
- `private <.ctor>b__6_9() : System.Decimal`  
- `private ConsumeCurrentEntry() : System.Void`  
- `public virtual Dispose() : System.Void`  
- `public virtual EnterArray(System.Int64& length) : System.Boolean`  
- `public virtual EnterNode(System.Type& type) : System.Boolean`  
- `public virtual ExitArray() : System.Boolean`  
- `public virtual ExitNode() : System.Boolean`  
- `public virtual GetDataDump() : System.String`  
- `public virtual PeekEntry(System.ReadOnlySpan`1[[System.Char, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& name) : Colossal.OdinSerializer.EntryType`  
- `protected virtual PeekEntry() : Colossal.OdinSerializer.EntryType`  
- `public virtual PrepareNewSerializationSession() : System.Void`  
- `public virtual ReadBoolean(System.Boolean& value) : System.Boolean`  
- `public virtual ReadByte(System.Byte& value) : System.Boolean`  
- `public virtual ReadChar(System.Char& value) : System.Boolean`  
- `public virtual ReadDecimal(System.Decimal& value) : System.Boolean`  
- `public virtual ReadDouble(System.Double& value) : System.Boolean`  
- `public virtual ReadExternalReference(System.Guid& guid) : System.Boolean`  
- `public virtual ReadExternalReference(System.String& id) : System.Boolean`  
- `public virtual ReadExternalReference(System.Int32& index) : System.Boolean`  
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
- `protected virtual ReadToNextEntry() : Colossal.OdinSerializer.EntryType`  
- `public virtual ReadUInt16(System.UInt16& value) : System.Boolean`  
- `public virtual ReadUInt32(System.UInt32& value) : System.Boolean`  
- `public virtual ReadUInt64(System.UInt64& value) : System.Boolean`  

