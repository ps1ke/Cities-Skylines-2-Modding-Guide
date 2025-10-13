# Colossal.Json.Decoder

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Json`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public sealed class Decoder : System.IDisposable
{
    private Colossal.Json.PositionTrackingStringReader json;
    private System.Int32 posStart;
    private System.Int32 rows;
    private System.Int32 columns;
    private System.Boolean prevWasNewLine;
    private static const System.String whiteSpace;
    private static const System.String wordBreak;

    private Decoder(System.String jsonString);

    private System.Void ConsumeWhiteSpace();
    public static Colossal.Json.Variant Decode(System.String jsonString);
    private Colossal.Json.ProxyArray DecodeArray();
    private Colossal.Json.Variant DecodeByToken(Colossal.Json.Decoder+Token token);
    private Colossal.Json.Variant DecodeNumber();
    private Colossal.Json.ProxyObject DecodeObject();
    private Colossal.Json.Variant DecodeString();
    private Colossal.Json.Variant DecodeValue();
    public System.Void Dispose();
    private System.Int32 JsonRead();
    private System.Char NextChar();
    private Colossal.Json.Decoder+Token NextToken();
    private System.String NextWord();
    private System.Char PeekChar();
    private System.Void UnexpectedEndException(System.Int32 row, System.Int32 column);
    private System.Void UnexpectedSymbolException(System.Int32 row, System.Int32 column);
}
```


## Fields

- `private Colossal.Json.PositionTrackingStringReader json`  

```csharp
private Colossal.Json.PositionTrackingStringReader json;
```

- `private System.Int32 posStart`  

```csharp
private System.Int32 posStart;
```

- `private System.Int32 rows`  

```csharp
private System.Int32 rows;
```

- `private System.Int32 columns`  

```csharp
private System.Int32 columns;
```

- `private System.Boolean prevWasNewLine`  

```csharp
private System.Boolean prevWasNewLine;
```

- `private static const System.String whiteSpace`  

```csharp
private static const System.String whiteSpace;
```

- `private static const System.String wordBreak`  

```csharp
private static const System.String wordBreak;
```


## Constructors

- `private Decoder(System.String jsonString)`  

```csharp
private Decoder(System.String jsonString);
```


## Methods

- `private ConsumeWhiteSpace() : System.Void`  

```csharp
private System.Void ConsumeWhiteSpace();
```

- `public static Decode(System.String jsonString) : Colossal.Json.Variant`  

```csharp
public static Colossal.Json.Variant Decode(System.String jsonString);
```

- `private DecodeArray() : Colossal.Json.ProxyArray`  

```csharp
private Colossal.Json.ProxyArray DecodeArray();
```

- `private DecodeByToken(Colossal.Json.Decoder+Token token) : Colossal.Json.Variant`  

```csharp
private Colossal.Json.Variant DecodeByToken(Colossal.Json.Decoder+Token token);
```

- `private DecodeNumber() : Colossal.Json.Variant`  

```csharp
private Colossal.Json.Variant DecodeNumber();
```

- `private DecodeObject() : Colossal.Json.ProxyObject`  

```csharp
private Colossal.Json.ProxyObject DecodeObject();
```

- `private DecodeString() : Colossal.Json.Variant`  

```csharp
private Colossal.Json.Variant DecodeString();
```

- `private DecodeValue() : Colossal.Json.Variant`  

```csharp
private Colossal.Json.Variant DecodeValue();
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `private JsonRead() : System.Int32`  

```csharp
private System.Int32 JsonRead();
```

- `private NextChar() : System.Char`  

```csharp
private System.Char NextChar();
```

- `private NextToken() : Colossal.Json.Decoder+Token`  

```csharp
private Colossal.Json.Decoder+Token NextToken();
```

- `private NextWord() : System.String`  

```csharp
private System.String NextWord();
```

- `private PeekChar() : System.Char`  

```csharp
private System.Char PeekChar();
```

- `private UnexpectedEndException(System.Int32 row, System.Int32 column) : System.Void`  

```csharp
private System.Void UnexpectedEndException(System.Int32 row, System.Int32 column);
```

- `private UnexpectedSymbolException(System.Int32 row, System.Int32 column) : System.Void`  

```csharp
private System.Void UnexpectedSymbolException(System.Int32 row, System.Int32 column);
```


## Nested types

- `Colossal.Json.Decoder+Token`  
- `Colossal.Json.Decoder+JSONFormatUnexpectedEndException`  
- `Colossal.Json.Decoder+JSONFormatUnexpectedSymbolException`  

