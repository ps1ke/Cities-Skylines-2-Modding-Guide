# Colossal.OdinSerializer.JsonDataReader

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.BaseDataReader`  
**Implements:** `Colossal.OdinSerializer.IDataReader`, `System.IDisposable`  

## Fields

- `private Colossal.OdinSerializer.JsonTextReader reader`  
- `private System.Nullable<Colossal.OdinSerializer.EntryType> peekedEntryType`  
- `private System.Char[] peekedEntryNameBuf`  
- `private System.Int32 peekedEntryNameLength`  
- `private System.Char[] peekedEntryContentBuf`  
- `private System.Int32 peekedEntryContentLength`  
- `private System.Collections.Generic.Dictionary<System.Int32, System.Type> seenTypes`  
- `private readonly System.Collections.Generic.Dictionary<System.Type, System.Delegate> primitiveArrayReaders`  

## Properties

- `private System.ReadOnlySpan<System.Char> peekedEntryName { private get }`  
- `private System.ReadOnlySpan<System.Char> peekedEntryContent { private get }`  
- `public System.IO.Stream Stream { get; set }`  

## Constructors

- `public JsonDataReader()`  
- `public JsonDataReader(System.IO.Stream stream, Colossal.OdinSerializer.DeserializationContext context)`  

## Methods

- `private <.ctor>b__13_0() : System.Char`  
- `private <.ctor>b__13_1() : System.SByte`  
- `private <.ctor>b__13_10() : System.Boolean`  
- `private <.ctor>b__13_11() : System.Single`  
- `private <.ctor>b__13_12() : System.Double`  
- `private <.ctor>b__13_13() : System.Guid`  
- `private <.ctor>b__13_2() : System.Int16`  
- `private <.ctor>b__13_3() : System.Int32`  
- `private <.ctor>b__13_4() : System.Int64`  
- `private <.ctor>b__13_5() : System.Byte`  
- `private <.ctor>b__13_6() : System.UInt16`  
- `private <.ctor>b__13_7() : System.UInt32`  
- `private <.ctor>b__13_8() : System.UInt64`  
- `private <.ctor>b__13_9() : System.Decimal`  
- `public virtual Dispose() : System.Void`  
- `public virtual EnterArray(System.Int64& length) : System.Boolean`  
- `public virtual EnterNode(System.Type& type) : System.Boolean`  
- `public virtual ExitArray() : System.Boolean`  
- `public virtual ExitNode() : System.Boolean`  
- `public virtual GetDataDump() : System.String`  
- `private MarkEntryConsumed() : System.Void`  
- `public virtual PeekEntry(System.ReadOnlySpan`1[[System.Char, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& name) : Colossal.OdinSerializer.EntryType`  
- `protected virtual PeekEntry() : Colossal.OdinSerializer.EntryType`  
- `public virtual PrepareNewSerializationSession() : System.Void`  
- `private ReadAnyIntReference(System.Int32& value) : System.Boolean`  
- `public virtual ReadBoolean(System.Boolean& value) : System.Boolean`  
- `public virtual ReadByte(System.Byte& value) : System.Boolean`  
- `public virtual ReadChar(System.Char& value) : System.Boolean`  
- `public virtual ReadDecimal(System.Decimal& value) : System.Boolean`  
- `public virtual ReadDouble(System.Double& value) : System.Boolean`  
- `public virtual ReadExternalReference(System.Int32& index) : System.Boolean`  
- `public virtual ReadExternalReference(System.Guid& guid) : System.Boolean`  
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
- `protected virtual ReadToNextEntry() : Colossal.OdinSerializer.EntryType`  
- `public virtual ReadUInt16(System.UInt16& value) : System.Boolean`  
- `public virtual ReadUInt32(System.UInt32& value) : System.Boolean`  
- `public virtual ReadUInt64(System.UInt64& value) : System.Boolean`  

