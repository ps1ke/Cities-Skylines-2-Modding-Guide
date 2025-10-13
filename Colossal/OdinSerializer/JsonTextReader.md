# Colossal.OdinSerializer.JsonTextReader

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class JsonTextReader : System.IDisposable
{
    private System.IO.StreamReader reader;
    private System.Int32 bufferIndex;
    private System.Char[] buffer;
    private System.Boolean lastReadCharValid;
    private System.Char lastReadChar;
    private System.Boolean peekedCharValid;
    private System.Char peekedChar;
    private System.Collections.Generic.Queue<System.Char> emergencyPlayback;
    private Colossal.OdinSerializer.DeserializationContext <Context>k__BackingField;
    private static readonly System.Collections.Generic.Dictionary<System.Char, System.Nullable<Colossal.OdinSerializer.EntryType>> EntryDelineators;
    private static readonly System.Collections.Generic.Dictionary<System.Char, System.Char> UnescapeDictionary;

    public Colossal.OdinSerializer.DeserializationContext Context { get; private set; }

    public JsonTextReader(System.IO.Stream stream, Colossal.OdinSerializer.DeserializationContext context);

    private System.Char ConsumeChar();
    private static System.Boolean Contains(System.ReadOnlySpan<System.Char> chars, System.Char c);
    public System.Void Dispose();
    private System.Nullable<Colossal.OdinSerializer.EntryType> GuessPrimitiveType(System.ReadOnlySpan<System.Char> content);
    private System.Boolean IsHex(System.Char c);
    private System.Void ParseEntryFromBuffer(System.ReadOnlySpan`1[[System.Char, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& name, System.ReadOnlySpan`1[[System.Char, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& valueContent, Colossal.OdinSerializer.EntryType& entry, System.Int32 valueSeparatorIndex, System.Nullable<Colossal.OdinSerializer.EntryType> hintEntry);
    private System.Char ParseHexChar(System.Char c1, System.Char c2, System.Char c3, System.Char c4);
    private System.UInt32 ParseSingleChar(System.Char c, System.UInt32 multiplier);
    private System.Char PeekChar();
    private System.Char ReadCharIntoBuffer();
    public System.Void ReadToNextEntry(System.ReadOnlySpan`1[[System.Char, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& name, System.ReadOnlySpan`1[[System.Char, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& valueContent, Colossal.OdinSerializer.EntryType& entry);
    public System.Void Reset();
    private System.Void SkipChar();
}
```


## Fields

- `private System.IO.StreamReader reader`  

```csharp
private System.IO.StreamReader reader;
```

- `private System.Int32 bufferIndex`  

```csharp
private System.Int32 bufferIndex;
```

- `private System.Char[] buffer`  

```csharp
private System.Char[] buffer;
```

- `private System.Boolean lastReadCharValid`  

```csharp
private System.Boolean lastReadCharValid;
```

- `private System.Char lastReadChar`  

```csharp
private System.Char lastReadChar;
```

- `private System.Boolean peekedCharValid`  

```csharp
private System.Boolean peekedCharValid;
```

- `private System.Char peekedChar`  

```csharp
private System.Char peekedChar;
```

- `private System.Collections.Generic.Queue<System.Char> emergencyPlayback`  

```csharp
private System.Collections.Generic.Queue<System.Char> emergencyPlayback;
```

- `private Colossal.OdinSerializer.DeserializationContext <Context>k__BackingField`  

```csharp
private Colossal.OdinSerializer.DeserializationContext <Context>k__BackingField;
```

- `private static readonly System.Collections.Generic.Dictionary<System.Char, System.Nullable<Colossal.OdinSerializer.EntryType>> EntryDelineators`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.Char, System.Nullable<Colossal.OdinSerializer.EntryType>> EntryDelineators;
```

- `private static readonly System.Collections.Generic.Dictionary<System.Char, System.Char> UnescapeDictionary`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.Char, System.Char> UnescapeDictionary;
```


## Properties

- `public Colossal.OdinSerializer.DeserializationContext Context { get; private set }`  

```csharp
public Colossal.OdinSerializer.DeserializationContext Context { get; private set; }
```


## Constructors

- `public JsonTextReader(System.IO.Stream stream, Colossal.OdinSerializer.DeserializationContext context)`  

```csharp
public JsonTextReader(System.IO.Stream stream, Colossal.OdinSerializer.DeserializationContext context);
```


## Methods

- `private ConsumeChar() : System.Char`  

```csharp
private System.Char ConsumeChar();
```

- `private static Contains(System.ReadOnlySpan<System.Char> chars, System.Char c) : System.Boolean`  

```csharp
private static System.Boolean Contains(System.ReadOnlySpan<System.Char> chars, System.Char c);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `private GuessPrimitiveType(System.ReadOnlySpan<System.Char> content) : System.Nullable<Colossal.OdinSerializer.EntryType>`  

```csharp
private System.Nullable<Colossal.OdinSerializer.EntryType> GuessPrimitiveType(System.ReadOnlySpan<System.Char> content);
```

- `private IsHex(System.Char c) : System.Boolean`  

```csharp
private System.Boolean IsHex(System.Char c);
```

- `private ParseEntryFromBuffer(System.ReadOnlySpan`1[[System.Char, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& name, System.ReadOnlySpan`1[[System.Char, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& valueContent, Colossal.OdinSerializer.EntryType& entry, System.Int32 valueSeparatorIndex, System.Nullable<Colossal.OdinSerializer.EntryType> hintEntry) : System.Void`  

```csharp
private System.Void ParseEntryFromBuffer(System.ReadOnlySpan`1[[System.Char, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& name, System.ReadOnlySpan`1[[System.Char, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& valueContent, Colossal.OdinSerializer.EntryType& entry, System.Int32 valueSeparatorIndex, System.Nullable<Colossal.OdinSerializer.EntryType> hintEntry);
```

- `private ParseHexChar(System.Char c1, System.Char c2, System.Char c3, System.Char c4) : System.Char`  

```csharp
private System.Char ParseHexChar(System.Char c1, System.Char c2, System.Char c3, System.Char c4);
```

- `private ParseSingleChar(System.Char c, System.UInt32 multiplier) : System.UInt32`  

```csharp
private System.UInt32 ParseSingleChar(System.Char c, System.UInt32 multiplier);
```

- `private PeekChar() : System.Char`  

```csharp
private System.Char PeekChar();
```

- `private ReadCharIntoBuffer() : System.Char`  

```csharp
private System.Char ReadCharIntoBuffer();
```

- `public ReadToNextEntry(System.ReadOnlySpan`1[[System.Char, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& name, System.ReadOnlySpan`1[[System.Char, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& valueContent, Colossal.OdinSerializer.EntryType& entry) : System.Void`  

```csharp
public System.Void ReadToNextEntry(System.ReadOnlySpan`1[[System.Char, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& name, System.ReadOnlySpan`1[[System.Char, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& valueContent, Colossal.OdinSerializer.EntryType& entry);
```

- `public Reset() : System.Void`  

```csharp
public System.Void Reset();
```

- `private SkipChar() : System.Void`  

```csharp
private System.Void SkipChar();
```


