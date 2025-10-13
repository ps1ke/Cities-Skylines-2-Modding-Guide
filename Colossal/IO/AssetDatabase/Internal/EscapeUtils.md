# Colossal.IO.AssetDatabase.Internal.EscapeUtils

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.Internal`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class EscapeUtils
{
    private static readonly System.String kReservedCharacters;
    private static readonly System.Char[] HexUpperChars;
    private static const System.Char kDummyChar;
    private static const System.Int16 c_MaxAsciiCharsReallocate;
    private static const System.Int16 c_MaxUnicodeCharsReallocate;
    private static const System.Int16 c_MaxUTF_8BytesPerUnicodeChar;
    private static const System.Int16 c_EncodedCharsPerByte;
    private static const System.Int32 c_MaxUriBufferSize;

    private static System.Char[] EnsureDestinationSize(System.Char* pStr, System.Char[] dest, System.Int32 currentInputPos, System.Int16 charsToAdd, System.Int16 minReallocateChars, System.Int32& destPos, System.Int32 prevInputPos);
    private static System.Void EscapeAsciiChar(System.Char ch, System.Char[] to, System.Int32& pos, System.Char escapeChar);
    private static System.Char EscapedAscii(System.Char digit, System.Char next);
    public static System.String EscapeString(System.String stringToEscape, System.Char escapeChar, System.Boolean encodeUnicode);
    public static System.String EscapeString(System.String stringToEscape, System.Char escapeChar, System.String reserved, System.Boolean encodeUnicode);
    private static System.Char[] EscapeString(System.String input, System.Int32 start, System.Int32 end, System.Char[] dest, System.Int32& destPos, System.Char escapeChar, System.String reserved, System.Boolean encodeUnicode);
    private static System.Boolean IsAsciiLetter(System.Char character);
    private static System.Boolean IsAsciiLetterOrDigit(System.Char character);
    private static System.Boolean IsReserved(System.Char c, System.String reserved);
    private static System.Void MatchUTF8Sequence(System.Char* pDest, System.Char[] dest, System.Int32& destOffset, System.Char[] unescapedChars, System.Int32 charCount, System.Byte[] bytes, System.Int32 byteCount, System.Char escapeChar);
    public static System.String UnescapeString(System.String stringToUnescape, System.Char escapeChar);
    private static System.Char[] UnescapeString(System.String input, System.Int32 start, System.Int32 end, System.Char[] dest, System.Int32& destPosition, System.Char escapeChar);
    internal static System.Char[] UnescapeString(System.Char* pStr, System.Int32 start, System.Int32 end, System.Char[] dest, System.Int32& destPosition, System.Char escapeChar);
}
```


## Fields

- `private static readonly System.String kReservedCharacters`  

```csharp
private static readonly System.String kReservedCharacters;
```

- `private static readonly System.Char[] HexUpperChars`  

```csharp
private static readonly System.Char[] HexUpperChars;
```

- `private static const System.Char kDummyChar`  

```csharp
private static const System.Char kDummyChar;
```

- `private static const System.Int16 c_MaxAsciiCharsReallocate`  

```csharp
private static const System.Int16 c_MaxAsciiCharsReallocate;
```

- `private static const System.Int16 c_MaxUnicodeCharsReallocate`  

```csharp
private static const System.Int16 c_MaxUnicodeCharsReallocate;
```

- `private static const System.Int16 c_MaxUTF_8BytesPerUnicodeChar`  

```csharp
private static const System.Int16 c_MaxUTF_8BytesPerUnicodeChar;
```

- `private static const System.Int16 c_EncodedCharsPerByte`  

```csharp
private static const System.Int16 c_EncodedCharsPerByte;
```

- `private static const System.Int32 c_MaxUriBufferSize`  

```csharp
private static const System.Int32 c_MaxUriBufferSize;
```


## Methods

- `private static EnsureDestinationSize(System.Char* pStr, System.Char[] dest, System.Int32 currentInputPos, System.Int16 charsToAdd, System.Int16 minReallocateChars, System.Int32& destPos, System.Int32 prevInputPos) : System.Char[]`  

```csharp
private static System.Char[] EnsureDestinationSize(System.Char* pStr, System.Char[] dest, System.Int32 currentInputPos, System.Int16 charsToAdd, System.Int16 minReallocateChars, System.Int32& destPos, System.Int32 prevInputPos);
```

- `private static EscapeAsciiChar(System.Char ch, System.Char[] to, System.Int32& pos, System.Char escapeChar) : System.Void`  

```csharp
private static System.Void EscapeAsciiChar(System.Char ch, System.Char[] to, System.Int32& pos, System.Char escapeChar);
```

- `private static EscapedAscii(System.Char digit, System.Char next) : System.Char`  

```csharp
private static System.Char EscapedAscii(System.Char digit, System.Char next);
```

- `public static EscapeString(System.String stringToEscape, System.Char escapeChar = %, System.Boolean encodeUnicode = False) : System.String`  

```csharp
public static System.String EscapeString(System.String stringToEscape, System.Char escapeChar, System.Boolean encodeUnicode);
```

- `public static EscapeString(System.String stringToEscape, System.Char escapeChar, System.String reserved, System.Boolean encodeUnicode) : System.String`  

```csharp
public static System.String EscapeString(System.String stringToEscape, System.Char escapeChar, System.String reserved, System.Boolean encodeUnicode);
```

- `private static EscapeString(System.String input, System.Int32 start, System.Int32 end, System.Char[] dest, System.Int32& destPos, System.Char escapeChar, System.String reserved, System.Boolean encodeUnicode) : System.Char[]`  

```csharp
private static System.Char[] EscapeString(System.String input, System.Int32 start, System.Int32 end, System.Char[] dest, System.Int32& destPos, System.Char escapeChar, System.String reserved, System.Boolean encodeUnicode);
```

- `private static IsAsciiLetter(System.Char character) : System.Boolean`  

```csharp
private static System.Boolean IsAsciiLetter(System.Char character);
```

- `private static IsAsciiLetterOrDigit(System.Char character) : System.Boolean`  

```csharp
private static System.Boolean IsAsciiLetterOrDigit(System.Char character);
```

- `private static IsReserved(System.Char c, System.String reserved) : System.Boolean`  

```csharp
private static System.Boolean IsReserved(System.Char c, System.String reserved);
```

- `private static MatchUTF8Sequence(System.Char* pDest, System.Char[] dest, System.Int32& destOffset, System.Char[] unescapedChars, System.Int32 charCount, System.Byte[] bytes, System.Int32 byteCount, System.Char escapeChar) : System.Void`  

```csharp
private static System.Void MatchUTF8Sequence(System.Char* pDest, System.Char[] dest, System.Int32& destOffset, System.Char[] unescapedChars, System.Int32 charCount, System.Byte[] bytes, System.Int32 byteCount, System.Char escapeChar);
```

- `public static UnescapeString(System.String stringToUnescape, System.Char escapeChar = %) : System.String`  

```csharp
public static System.String UnescapeString(System.String stringToUnescape, System.Char escapeChar);
```

- `private static UnescapeString(System.String input, System.Int32 start, System.Int32 end, System.Char[] dest, System.Int32& destPosition, System.Char escapeChar) : System.Char[]`  

```csharp
private static System.Char[] UnescapeString(System.String input, System.Int32 start, System.Int32 end, System.Char[] dest, System.Int32& destPosition, System.Char escapeChar);
```

- `internal static UnescapeString(System.Char* pStr, System.Int32 start, System.Int32 end, System.Char[] dest, System.Int32& destPosition, System.Char escapeChar) : System.Char[]`  

```csharp
internal static System.Char[] UnescapeString(System.Char* pStr, System.Int32 start, System.Int32 end, System.Char[] dest, System.Int32& destPosition, System.Char escapeChar);
```


