# Colossal.IO.AssetDatabase.COCParser

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private System.String m_Source`  
- `private System.Int32 m_Index`  
- `private System.Int32 m_Line`  
- `private System.Int32 m_Column`  
- `private System.Int32 m_CurrentLine`  
- `private System.Int32 m_CurrentColumn`  
- `private static readonly System.Char[] kNewLine`  
- `private static readonly System.Char[] kTrimCharacters`  
- `private static readonly System.Char[] kWhiteSpaceCharacters`  
- `private static readonly System.Char[] kInvalidCharacters`  
- `private static const System.Char kObjectStart`  
- `private static const System.Char kObjectEnd`  
- `private static const System.Char kQuotes`  
- `private static const System.Char kBackSlash`  
- `private static const System.Char kPlatformAgnosticNewline`  
- `private static const System.Char kLineReturn`  
- `private static const System.String kUniqueNameChars`  

## Constructors

- `public COCParser()`  

## Methods

- `private Advance() : System.Char`  
- `private FindCharacter(System.Char chr, System.Char[] characters) : System.Boolean`  
- `private FindOpenBrace() : System.Boolean`  
- `private static MakeUniqueName(System.String name, System.Int32 length) : System.String`  
- `public Parse(System.String source, System.Collections.Generic.IReadOnlyList`1[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& outReport) : System.Collections.Generic.Dictionary<System.String, Colossal.IO.AssetDatabase.COCParser+ObjectBlock>`  
- `private ParseName(System.Int32& nameStart, System.Int32& nameEnd) : System.Boolean`  
- `private ParseObject(System.Int32& startIndex, System.Int32& length) : System.Void`  
- `private Peek(System.Int32 offset = 0) : System.Char`  
- `private Trim(System.Char[] characters) : System.Boolean`  

## Nested types

- `Colossal.IO.AssetDatabase.COCParser+COCParserUnexpectedEndException`  
- `Colossal.IO.AssetDatabase.COCParser+ObjectBlock`  

