# Colossal.Json.Decoder

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Json`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Fields

- `private Colossal.Json.PositionTrackingStringReader json`  
- `private System.Int32 posStart`  
- `private System.Int32 rows`  
- `private System.Int32 columns`  
- `private System.Boolean prevWasNewLine`  
- `private static const System.String whiteSpace`  
- `private static const System.String wordBreak`  

## Constructors

- `private Decoder(System.String jsonString)`  

## Methods

- `private ConsumeWhiteSpace() : System.Void`  
- `public static Decode(System.String jsonString) : Colossal.Json.Variant`  
- `private DecodeArray() : Colossal.Json.ProxyArray`  
- `private DecodeByToken(Colossal.Json.Decoder+Token token) : Colossal.Json.Variant`  
- `private DecodeNumber() : Colossal.Json.Variant`  
- `private DecodeObject() : Colossal.Json.ProxyObject`  
- `private DecodeString() : Colossal.Json.Variant`  
- `private DecodeValue() : Colossal.Json.Variant`  
- `public Dispose() : System.Void`  
- `private JsonRead() : System.Int32`  
- `private NextChar() : System.Char`  
- `private NextToken() : Colossal.Json.Decoder+Token`  
- `private NextWord() : System.String`  
- `private PeekChar() : System.Char`  
- `private UnexpectedEndException(System.Int32 row, System.Int32 column) : System.Void`  
- `private UnexpectedSymbolException(System.Int32 row, System.Int32 column) : System.Void`  

## Nested types

- `Colossal.Json.Decoder+Token`  
- `Colossal.Json.Decoder+JSONFormatUnexpectedEndException`  
- `Colossal.Json.Decoder+JSONFormatUnexpectedSymbolException`  

