# Colossal.IO.AssetDatabase.Internal.EscapeUtils

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.Internal`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `private static readonly System.String kReservedCharacters`  
- `private static readonly System.Char[] HexUpperChars`  
- `private static const System.Char kDummyChar`  
- `private static const System.Int16 c_MaxAsciiCharsReallocate`  
- `private static const System.Int16 c_MaxUnicodeCharsReallocate`  
- `private static const System.Int16 c_MaxUTF_8BytesPerUnicodeChar`  
- `private static const System.Int16 c_EncodedCharsPerByte`  
- `private static const System.Int32 c_MaxUriBufferSize`  

## Methods

- `private static EnsureDestinationSize(System.Char* pStr, System.Char[] dest, System.Int32 currentInputPos, System.Int16 charsToAdd, System.Int16 minReallocateChars, System.Int32& destPos, System.Int32 prevInputPos) : System.Char[]`  
- `private static EscapeAsciiChar(System.Char ch, System.Char[] to, System.Int32& pos, System.Char escapeChar) : System.Void`  
- `private static EscapedAscii(System.Char digit, System.Char next) : System.Char`  
- `public static EscapeString(System.String stringToEscape, System.Char escapeChar = %, System.Boolean encodeUnicode = False) : System.String`  
- `public static EscapeString(System.String stringToEscape, System.Char escapeChar, System.String reserved, System.Boolean encodeUnicode) : System.String`  
- `private static EscapeString(System.String input, System.Int32 start, System.Int32 end, System.Char[] dest, System.Int32& destPos, System.Char escapeChar, System.String reserved, System.Boolean encodeUnicode) : System.Char[]`  
- `private static IsAsciiLetter(System.Char character) : System.Boolean`  
- `private static IsAsciiLetterOrDigit(System.Char character) : System.Boolean`  
- `private static IsReserved(System.Char c, System.String reserved) : System.Boolean`  
- `private static MatchUTF8Sequence(System.Char* pDest, System.Char[] dest, System.Int32& destOffset, System.Char[] unescapedChars, System.Int32 charCount, System.Byte[] bytes, System.Int32 byteCount, System.Char escapeChar) : System.Void`  
- `public static UnescapeString(System.String stringToUnescape, System.Char escapeChar = %) : System.String`  
- `private static UnescapeString(System.String input, System.Int32 start, System.Int32 end, System.Char[] dest, System.Int32& destPosition, System.Char escapeChar) : System.Char[]`  
- `internal static UnescapeString(System.Char* pStr, System.Int32 start, System.Int32 end, System.Char[] dest, System.Int32& destPosition, System.Char escapeChar) : System.Char[]`  

