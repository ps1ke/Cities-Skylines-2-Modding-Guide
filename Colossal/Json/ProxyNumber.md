# Colossal.Json.ProxyNumber

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Json`  

**Type:** class sealed public  

**Base:** `Colossal.Json.Variant`  
**Implements:** `System.IConvertible`, `System.IEquatable<Colossal.Json.Variant>`  

## Code

```csharp
public sealed class ProxyNumber : Colossal.Json.Variant, System.IConvertible, System.IEquatable<Colossal.Json.Variant>
{
    private readonly System.IConvertible value;
    private static readonly System.Char[] floatingPointCharacters;

    public ProxyNumber(System.IConvertible value);

    public virtual System.Boolean Equals(Colossal.Json.Variant other);
    private static System.IConvertible Parse(System.String value);
    public virtual System.Boolean ToBoolean(System.IFormatProvider provider);
    public virtual System.Byte ToByte(System.IFormatProvider provider);
    public virtual System.Char ToChar(System.IFormatProvider provider);
    public virtual System.Decimal ToDecimal(System.IFormatProvider provider);
    public virtual System.Double ToDouble(System.IFormatProvider provider);
    public virtual System.Int16 ToInt16(System.IFormatProvider provider);
    public virtual System.Int32 ToInt32(System.IFormatProvider provider);
    public virtual System.Int64 ToInt64(System.IFormatProvider provider);
    public virtual System.SByte ToSByte(System.IFormatProvider provider);
    public virtual System.Single ToSingle(System.IFormatProvider provider);
    public virtual System.String ToString(System.IFormatProvider provider);
    public virtual System.UInt16 ToUInt16(System.IFormatProvider provider);
    public virtual System.UInt32 ToUInt32(System.IFormatProvider provider);
    public virtual System.UInt64 ToUInt64(System.IFormatProvider provider);
}
```


## Fields

- `private readonly System.IConvertible value`  

```csharp
private readonly System.IConvertible value;
```

- `private static readonly System.Char[] floatingPointCharacters`  

```csharp
private static readonly System.Char[] floatingPointCharacters;
```


## Constructors

- `public ProxyNumber(System.IConvertible value)`  

```csharp
public ProxyNumber(System.IConvertible value);
```


## Methods

- `public virtual Equals(Colossal.Json.Variant other) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(Colossal.Json.Variant other);
```

- `private static Parse(System.String value) : System.IConvertible`  

```csharp
private static System.IConvertible Parse(System.String value);
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


