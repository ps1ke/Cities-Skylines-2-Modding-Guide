# Colossal.Json.Encoder

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Json`  

**Type:** class sealed public  

**Base:** `System.Object`  

## Code

```csharp
public sealed class Encoder
{
    private readonly System.Text.StringBuilder builder;
    private readonly Colossal.Json.EncodeOptions options;
    private System.Int32 indent;
    private static readonly System.Collections.Generic.HashSet<System.Type> m_PrimitiveTypes;

    private System.Boolean isCompactPrintEnabled { private get; }
    private System.Boolean isForceTypeHintsEnabled { private get; }

    private Encoder(Colossal.Json.EncodeOptions options);

    private System.Void AppendCloseBrace();
    private System.Void AppendCloseBracket();
    private System.Void AppendColon();
    private System.Void AppendComma(System.Boolean firstItem);
    private System.Void AppendIndent();
    private System.Void AppendOpenBrace();
    private System.Void AppendOpenBracket();
    public static System.String Encode(System.Object obj, Colossal.Json.EncodeOptions options);
    private System.Void EncodeArray(System.Array value, System.Boolean forceTypeHint);
    private System.Void EncodeArrayRank(System.Array value, System.Int32 rank, System.Int32[] indices, System.Boolean forceTypeHint);
    private System.Void EncodeDictionary(System.Collections.IDictionary value, System.Boolean forceTypeHint);
    private System.Void EncodeList(System.Collections.IList value, System.Boolean forceTypeHint);
    private System.Void EncodeObject(System.Object value, System.Boolean forceTypeHint);
    private System.Void EncodePropertyArray(System.Object value, System.Reflection.PropertyInfo property, System.Reflection.ParameterInfo[] parameters, System.Boolean forceTypeHint);
    private System.Void EncodeProxyArray(Colossal.Json.ProxyArray value);
    private System.Void EncodeProxyObject(Colossal.Json.ProxyObject value);
    private System.Void EncodeSet(System.Collections.IEnumerable value, System.Boolean forceTypeHint);
    private System.Void EncodeString(System.String value);
    private System.Void EncodeValue(System.Object value, System.Boolean forceTypeHint);
    private System.Boolean HasAny(System.Collections.IEnumerable value);
}
```


## Fields

- `private readonly System.Text.StringBuilder builder`  

```csharp
private readonly System.Text.StringBuilder builder;
```

- `private readonly Colossal.Json.EncodeOptions options`  

```csharp
private readonly Colossal.Json.EncodeOptions options;
```

- `private System.Int32 indent`  

```csharp
private System.Int32 indent;
```

- `private static readonly System.Collections.Generic.HashSet<System.Type> m_PrimitiveTypes`  

```csharp
private static readonly System.Collections.Generic.HashSet<System.Type> m_PrimitiveTypes;
```


## Properties

- `private System.Boolean isCompactPrintEnabled { private get }`  

```csharp
private System.Boolean isCompactPrintEnabled { private get; }
```

- `private System.Boolean isForceTypeHintsEnabled { private get }`  

```csharp
private System.Boolean isForceTypeHintsEnabled { private get; }
```


## Constructors

- `private Encoder(Colossal.Json.EncodeOptions options)`  

```csharp
private Encoder(Colossal.Json.EncodeOptions options);
```


## Methods

- `private AppendCloseBrace() : System.Void`  

```csharp
private System.Void AppendCloseBrace();
```

- `private AppendCloseBracket() : System.Void`  

```csharp
private System.Void AppendCloseBracket();
```

- `private AppendColon() : System.Void`  

```csharp
private System.Void AppendColon();
```

- `private AppendComma(System.Boolean firstItem) : System.Void`  

```csharp
private System.Void AppendComma(System.Boolean firstItem);
```

- `private AppendIndent() : System.Void`  

```csharp
private System.Void AppendIndent();
```

- `private AppendOpenBrace() : System.Void`  

```csharp
private System.Void AppendOpenBrace();
```

- `private AppendOpenBracket() : System.Void`  

```csharp
private System.Void AppendOpenBracket();
```

- `public static Encode(System.Object obj, Colossal.Json.EncodeOptions options) : System.String`  

```csharp
public static System.String Encode(System.Object obj, Colossal.Json.EncodeOptions options);
```

- `private EncodeArray(System.Array value, System.Boolean forceTypeHint) : System.Void`  

```csharp
private System.Void EncodeArray(System.Array value, System.Boolean forceTypeHint);
```

- `private EncodeArrayRank(System.Array value, System.Int32 rank, System.Int32[] indices, System.Boolean forceTypeHint) : System.Void`  

```csharp
private System.Void EncodeArrayRank(System.Array value, System.Int32 rank, System.Int32[] indices, System.Boolean forceTypeHint);
```

- `private EncodeDictionary(System.Collections.IDictionary value, System.Boolean forceTypeHint) : System.Void`  

```csharp
private System.Void EncodeDictionary(System.Collections.IDictionary value, System.Boolean forceTypeHint);
```

- `private EncodeList(System.Collections.IList value, System.Boolean forceTypeHint) : System.Void`  

```csharp
private System.Void EncodeList(System.Collections.IList value, System.Boolean forceTypeHint);
```

- `private EncodeObject(System.Object value, System.Boolean forceTypeHint) : System.Void`  

```csharp
private System.Void EncodeObject(System.Object value, System.Boolean forceTypeHint);
```

- `private EncodePropertyArray(System.Object value, System.Reflection.PropertyInfo property, System.Reflection.ParameterInfo[] parameters, System.Boolean forceTypeHint) : System.Void`  

```csharp
private System.Void EncodePropertyArray(System.Object value, System.Reflection.PropertyInfo property, System.Reflection.ParameterInfo[] parameters, System.Boolean forceTypeHint);
```

- `private EncodeProxyArray(Colossal.Json.ProxyArray value) : System.Void`  

```csharp
private System.Void EncodeProxyArray(Colossal.Json.ProxyArray value);
```

- `private EncodeProxyObject(Colossal.Json.ProxyObject value) : System.Void`  

```csharp
private System.Void EncodeProxyObject(Colossal.Json.ProxyObject value);
```

- `private EncodeSet(System.Collections.IEnumerable value, System.Boolean forceTypeHint) : System.Void`  

```csharp
private System.Void EncodeSet(System.Collections.IEnumerable value, System.Boolean forceTypeHint);
```

- `private EncodeString(System.String value) : System.Void`  

```csharp
private System.Void EncodeString(System.String value);
```

- `private EncodeValue(System.Object value, System.Boolean forceTypeHint) : System.Void`  

```csharp
private System.Void EncodeValue(System.Object value, System.Boolean forceTypeHint);
```

- `private HasAny(System.Collections.IEnumerable value) : System.Boolean`  

```csharp
private System.Boolean HasAny(System.Collections.IEnumerable value);
```


## Nested types

- `Colossal.Json.Encoder+<>c`  
- `Colossal.Json.Encoder+<>c__DisplayClass11_0`  

