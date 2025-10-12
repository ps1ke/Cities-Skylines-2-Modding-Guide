# Colossal.OdinSerializer.JsonTextReader

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Fields

- `private System.IO.StreamReader reader`  
- `private System.Int32 bufferIndex`  
- `private System.Char[] buffer`  
- `private System.Boolean lastReadCharValid`  
- `private System.Char lastReadChar`  
- `private System.Boolean peekedCharValid`  
- `private System.Char peekedChar`  
- `private System.Collections.Generic.Queue<System.Char> emergencyPlayback`  
- `private Colossal.OdinSerializer.DeserializationContext <Context>k__BackingField`  
- `private static readonly System.Collections.Generic.Dictionary<System.Char, System.Nullable<Colossal.OdinSerializer.EntryType>> EntryDelineators`  
- `private static readonly System.Collections.Generic.Dictionary<System.Char, System.Char> UnescapeDictionary`  

## Properties

- `public Colossal.OdinSerializer.DeserializationContext Context { get; private set }`  

## Constructors

- `public JsonTextReader(System.IO.Stream stream, Colossal.OdinSerializer.DeserializationContext context)`  

## Methods

- `private ConsumeChar() : System.Char`  
- `private static Contains(System.ReadOnlySpan<System.Char> chars, System.Char c) : System.Boolean`  
- `public Dispose() : System.Void`  
- `private GuessPrimitiveType(System.ReadOnlySpan<System.Char> content) : System.Nullable<Colossal.OdinSerializer.EntryType>`  
- `private IsHex(System.Char c) : System.Boolean`  
- `private ParseEntryFromBuffer(System.ReadOnlySpan`1[[System.Char, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& name, System.ReadOnlySpan`1[[System.Char, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& valueContent, Colossal.OdinSerializer.EntryType& entry, System.Int32 valueSeparatorIndex, System.Nullable<Colossal.OdinSerializer.EntryType> hintEntry) : System.Void`  
- `private ParseHexChar(System.Char c1, System.Char c2, System.Char c3, System.Char c4) : System.Char`  
- `private ParseSingleChar(System.Char c, System.UInt32 multiplier) : System.UInt32`  
- `private PeekChar() : System.Char`  
- `private ReadCharIntoBuffer() : System.Char`  
- `public ReadToNextEntry(System.ReadOnlySpan`1[[System.Char, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& name, System.ReadOnlySpan`1[[System.Char, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& valueContent, Colossal.OdinSerializer.EntryType& entry) : System.Void`  
- `public Reset() : System.Void`  
- `private SkipChar() : System.Void`  

