# Colossal.Json.Variant

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Json`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `System.IConvertible`, `System.IEquatable<Colossal.Json.Variant>`  

**Attributes:** `DefaultMember`  

## Code

```csharp
public abstract class Variant : System.IConvertible, System.IEquatable<Colossal.Json.Variant>
{
    protected static readonly System.IFormatProvider kFormatProvider;

    public System.Int32 Count { get; }
    public Colossal.Json.Variant Item { get; set; }
    public Colossal.Json.Variant Item { get; set; }

    protected Variant();

    public abstract System.Boolean Equals(Colossal.Json.Variant other);
    public virtual System.TypeCode GetTypeCode();
    public System.Void Make<T>(T& item);
    public T Make<T>();
    public virtual System.Boolean ToBoolean(System.IFormatProvider provider);
    public virtual System.Byte ToByte(System.IFormatProvider provider);
    public virtual System.Char ToChar(System.IFormatProvider provider);
    public virtual System.DateTime ToDateTime(System.IFormatProvider provider);
    public virtual System.Decimal ToDecimal(System.IFormatProvider provider);
    public virtual System.Double ToDouble(System.IFormatProvider provider);
    public virtual System.Int16 ToInt16(System.IFormatProvider provider);
    public virtual System.Int32 ToInt32(System.IFormatProvider provider);
    public virtual System.Int64 ToInt64(System.IFormatProvider provider);
    public System.String ToJSON();
    public System.String ToJSON(Colossal.Json.EncodeOptions options);
    public virtual System.SByte ToSByte(System.IFormatProvider provider);
    public virtual System.Single ToSingle(System.IFormatProvider provider);
    public virtual System.String ToString(System.IFormatProvider provider);
    public virtual System.String ToString();
    public virtual System.Object ToType(System.Type conversionType, System.IFormatProvider provider);
    public virtual System.UInt16 ToUInt16(System.IFormatProvider provider);
    public virtual System.UInt32 ToUInt32(System.IFormatProvider provider);
    public virtual System.UInt64 ToUInt64(System.IFormatProvider provider);
    public virtual Colossal.Json.Variant TryGet(System.String key);
    public virtual System.Boolean TryGetValue(System.String key, Colossal.Json.Variant& variant);
    public System.Void Write<T>(T& item);
}
```


## Fields

- `protected static readonly System.IFormatProvider kFormatProvider`  

```csharp
protected static readonly System.IFormatProvider kFormatProvider;
```


## Properties

- `public System.Int32 Count { get }`  

```csharp
public System.Int32 Count { get; }
```

- `public Colossal.Json.Variant Item { get; set }`  

```csharp
public Colossal.Json.Variant Item { get; set; }
```

- `public Colossal.Json.Variant Item { get; set }`  

```csharp
public Colossal.Json.Variant Item { get; set; }
```


## Constructors

- `protected Variant()`  

```csharp
protected Variant();
```


## Methods

- `public abstract Equals(Colossal.Json.Variant other) : System.Boolean`  

```csharp
public abstract System.Boolean Equals(Colossal.Json.Variant other);
```

- `public virtual GetTypeCode() : System.TypeCode`  

```csharp
public virtual System.TypeCode GetTypeCode();
```

- `public Make<T>(T& item) : System.Void`  

```csharp
public System.Void Make<T>(T& item);
```

- `public Make<T>() : T`  

```csharp
public T Make<T>();
```

- `public virtual ToBoolean(System.IFormatProvider provider) : System.Boolean`  

```csharp
public virtual System.Boolean ToBoolean(System.IFormatProvider provider);
```

- `public virtual ToByte(System.IFormatProvider provider) : System.Byte`  

```csharp
public virtual System.Byte ToByte(System.IFormatProvider provider);
```

- `public virtual ToChar(System.IFormatProvider provider) : System.Char`  

```csharp
public virtual System.Char ToChar(System.IFormatProvider provider);
```

- `public virtual ToDateTime(System.IFormatProvider provider) : System.DateTime`  

```csharp
public virtual System.DateTime ToDateTime(System.IFormatProvider provider);
```

- `public virtual ToDecimal(System.IFormatProvider provider) : System.Decimal`  

```csharp
public virtual System.Decimal ToDecimal(System.IFormatProvider provider);
```

- `public virtual ToDouble(System.IFormatProvider provider) : System.Double`  

```csharp
public virtual System.Double ToDouble(System.IFormatProvider provider);
```

- `public virtual ToInt16(System.IFormatProvider provider) : System.Int16`  

```csharp
public virtual System.Int16 ToInt16(System.IFormatProvider provider);
```

- `public virtual ToInt32(System.IFormatProvider provider) : System.Int32`  

```csharp
public virtual System.Int32 ToInt32(System.IFormatProvider provider);
```

- `public virtual ToInt64(System.IFormatProvider provider) : System.Int64`  

```csharp
public virtual System.Int64 ToInt64(System.IFormatProvider provider);
```

- `public ToJSON() : System.String`  

```csharp
public System.String ToJSON();
```

- `public ToJSON(Colossal.Json.EncodeOptions options) : System.String`  

```csharp
public System.String ToJSON(Colossal.Json.EncodeOptions options);
```

- `public virtual ToSByte(System.IFormatProvider provider) : System.SByte`  

```csharp
public virtual System.SByte ToSByte(System.IFormatProvider provider);
```

- `public virtual ToSingle(System.IFormatProvider provider) : System.Single`  

```csharp
public virtual System.Single ToSingle(System.IFormatProvider provider);
```

- `public virtual ToString(System.IFormatProvider provider) : System.String`  

```csharp
public virtual System.String ToString(System.IFormatProvider provider);
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```

- `public virtual ToType(System.Type conversionType, System.IFormatProvider provider) : System.Object`  

```csharp
public virtual System.Object ToType(System.Type conversionType, System.IFormatProvider provider);
```

- `public virtual ToUInt16(System.IFormatProvider provider) : System.UInt16`  

```csharp
public virtual System.UInt16 ToUInt16(System.IFormatProvider provider);
```

- `public virtual ToUInt32(System.IFormatProvider provider) : System.UInt32`  

```csharp
public virtual System.UInt32 ToUInt32(System.IFormatProvider provider);
```

- `public virtual ToUInt64(System.IFormatProvider provider) : System.UInt64`  

```csharp
public virtual System.UInt64 ToUInt64(System.IFormatProvider provider);
```

- `public virtual TryGet(System.String key) : Colossal.Json.Variant`  

```csharp
public virtual Colossal.Json.Variant TryGet(System.String key);
```

- `public virtual TryGetValue(System.String key, Colossal.Json.Variant& variant) : System.Boolean`  

```csharp
public virtual System.Boolean TryGetValue(System.String key, Colossal.Json.Variant& variant);
```

- `public Write<T>(T& item) : System.Void`  

```csharp
public System.Void Write<T>(T& item);
```


