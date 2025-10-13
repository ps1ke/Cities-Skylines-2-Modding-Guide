# Colossal.IO.AssetDatabase.COCParser

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class COCParser
{
    private System.String m_Source;
    private System.Int32 m_Index;
    private System.Int32 m_Line;
    private System.Int32 m_Column;
    private System.Int32 m_CurrentLine;
    private System.Int32 m_CurrentColumn;
    private static readonly System.Char[] kNewLine;
    private static readonly System.Char[] kTrimCharacters;
    private static readonly System.Char[] kWhiteSpaceCharacters;
    private static readonly System.Char[] kInvalidCharacters;
    private static const System.Char kObjectStart;
    private static const System.Char kObjectEnd;
    private static const System.Char kQuotes;
    private static const System.Char kBackSlash;
    private static const System.Char kPlatformAgnosticNewline;
    private static const System.Char kLineReturn;
    private static const System.String kUniqueNameChars;

    public COCParser();

    private System.Char Advance();
    private System.Boolean FindCharacter(System.Char chr, System.Char[] characters);
    private System.Boolean FindOpenBrace();
    private static System.String MakeUniqueName(System.String name, System.Int32 length);
    public System.Collections.Generic.Dictionary<System.String, Colossal.IO.AssetDatabase.COCParser+ObjectBlock> Parse(System.String source, System.Collections.Generic.IReadOnlyList`1[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& outReport);
    private System.Boolean ParseName(System.Int32& nameStart, System.Int32& nameEnd);
    private System.Void ParseObject(System.Int32& startIndex, System.Int32& length);
    private System.Char Peek(System.Int32 offset);
    private System.Boolean Trim(System.Char[] characters);
}
```


## Fields

- `private System.String m_Source`  

```csharp
private System.String m_Source;
```

- `private System.Int32 m_Index`  

```csharp
private System.Int32 m_Index;
```

- `private System.Int32 m_Line`  

```csharp
private System.Int32 m_Line;
```

- `private System.Int32 m_Column`  

```csharp
private System.Int32 m_Column;
```

- `private System.Int32 m_CurrentLine`  

```csharp
private System.Int32 m_CurrentLine;
```

- `private System.Int32 m_CurrentColumn`  

```csharp
private System.Int32 m_CurrentColumn;
```

- `private static readonly System.Char[] kNewLine`  

```csharp
private static readonly System.Char[] kNewLine;
```

- `private static readonly System.Char[] kTrimCharacters`  

```csharp
private static readonly System.Char[] kTrimCharacters;
```

- `private static readonly System.Char[] kWhiteSpaceCharacters`  

```csharp
private static readonly System.Char[] kWhiteSpaceCharacters;
```

- `private static readonly System.Char[] kInvalidCharacters`  

```csharp
private static readonly System.Char[] kInvalidCharacters;
```

- `private static const System.Char kObjectStart`  

```csharp
private static const System.Char kObjectStart;
```

- `private static const System.Char kObjectEnd`  

```csharp
private static const System.Char kObjectEnd;
```

- `private static const System.Char kQuotes`  

```csharp
private static const System.Char kQuotes;
```

- `private static const System.Char kBackSlash`  

```csharp
private static const System.Char kBackSlash;
```

- `private static const System.Char kPlatformAgnosticNewline`  

```csharp
private static const System.Char kPlatformAgnosticNewline;
```

- `private static const System.Char kLineReturn`  

```csharp
private static const System.Char kLineReturn;
```

- `private static const System.String kUniqueNameChars`  

```csharp
private static const System.String kUniqueNameChars;
```


## Constructors

- `public COCParser()`  

```csharp
public COCParser();
```


## Methods

- `private Advance() : System.Char`  

```csharp
private System.Char Advance();
```

- `private FindCharacter(System.Char chr, System.Char[] characters) : System.Boolean`  

```csharp
private System.Boolean FindCharacter(System.Char chr, System.Char[] characters);
```

- `private FindOpenBrace() : System.Boolean`  

```csharp
private System.Boolean FindOpenBrace();
```

- `private static MakeUniqueName(System.String name, System.Int32 length) : System.String`  

```csharp
private static System.String MakeUniqueName(System.String name, System.Int32 length);
```

- `public Parse(System.String source, System.Collections.Generic.IReadOnlyList`1[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& outReport) : System.Collections.Generic.Dictionary<System.String, Colossal.IO.AssetDatabase.COCParser+ObjectBlock>`  

```csharp
public System.Collections.Generic.Dictionary<System.String, Colossal.IO.AssetDatabase.COCParser+ObjectBlock> Parse(System.String source, System.Collections.Generic.IReadOnlyList`1[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& outReport);
```

- `private ParseName(System.Int32& nameStart, System.Int32& nameEnd) : System.Boolean`  

```csharp
private System.Boolean ParseName(System.Int32& nameStart, System.Int32& nameEnd);
```

- `private ParseObject(System.Int32& startIndex, System.Int32& length) : System.Void`  

```csharp
private System.Void ParseObject(System.Int32& startIndex, System.Int32& length);
```

- `private Peek(System.Int32 offset = 0) : System.Char`  

```csharp
private System.Char Peek(System.Int32 offset);
```

- `private Trim(System.Char[] characters) : System.Boolean`  

```csharp
private System.Boolean Trim(System.Char[] characters);
```


## Nested types

- `Colossal.IO.AssetDatabase.COCParser+COCParserUnexpectedEndException`  
- `Colossal.IO.AssetDatabase.COCParser+ObjectBlock`  

