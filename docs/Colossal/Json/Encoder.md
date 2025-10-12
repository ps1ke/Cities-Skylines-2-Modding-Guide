# Colossal.Json.Encoder

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Json`  

**Type:** class sealed public  

**Base:** `System.Object`  

## Fields

- `private readonly System.Text.StringBuilder builder`  
- `private readonly Colossal.Json.EncodeOptions options`  
- `private System.Int32 indent`  
- `private static readonly System.Collections.Generic.HashSet<System.Type> m_PrimitiveTypes`  

## Properties

- `private System.Boolean isCompactPrintEnabled { private get }`  
- `private System.Boolean isForceTypeHintsEnabled { private get }`  

## Constructors

- `private Encoder(Colossal.Json.EncodeOptions options)`  

## Methods

- `private AppendCloseBrace() : System.Void`  
- `private AppendCloseBracket() : System.Void`  
- `private AppendColon() : System.Void`  
- `private AppendComma(System.Boolean firstItem) : System.Void`  
- `private AppendIndent() : System.Void`  
- `private AppendOpenBrace() : System.Void`  
- `private AppendOpenBracket() : System.Void`  
- `public static Encode(System.Object obj, Colossal.Json.EncodeOptions options) : System.String`  
- `private EncodeArray(System.Array value, System.Boolean forceTypeHint) : System.Void`  
- `private EncodeArrayRank(System.Array value, System.Int32 rank, System.Int32[] indices, System.Boolean forceTypeHint) : System.Void`  
- `private EncodeDictionary(System.Collections.IDictionary value, System.Boolean forceTypeHint) : System.Void`  
- `private EncodeList(System.Collections.IList value, System.Boolean forceTypeHint) : System.Void`  
- `private EncodeObject(System.Object value, System.Boolean forceTypeHint) : System.Void`  
- `private EncodePropertyArray(System.Object value, System.Reflection.PropertyInfo property, System.Reflection.ParameterInfo[] parameters, System.Boolean forceTypeHint) : System.Void`  
- `private EncodeProxyArray(Colossal.Json.ProxyArray value) : System.Void`  
- `private EncodeProxyObject(Colossal.Json.ProxyObject value) : System.Void`  
- `private EncodeSet(System.Collections.IEnumerable value, System.Boolean forceTypeHint) : System.Void`  
- `private EncodeString(System.String value) : System.Void`  
- `private EncodeValue(System.Object value, System.Boolean forceTypeHint) : System.Void`  
- `private HasAny(System.Collections.IEnumerable value) : System.Boolean`  

## Nested types

- `Colossal.Json.Encoder+<>c`  
- `Colossal.Json.Encoder+<>c__DisplayClass11_0`  

