# Colossal.Json.Variant

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Json`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `System.IConvertible`, `System.IEquatable<Colossal.Json.Variant>`  

**Attributes:** `DefaultMember`  

## Fields

- `protected static readonly System.IFormatProvider kFormatProvider`  

## Properties

- `public System.Int32 Count { get }`  
- `public Colossal.Json.Variant Item { get; set }`  
- `public Colossal.Json.Variant Item { get; set }`  

## Constructors

- `protected Variant()`  

## Methods

- `public abstract Equals(Colossal.Json.Variant other) : System.Boolean`  
- `public virtual GetTypeCode() : System.TypeCode`  
- `public Make<T>(T& item) : System.Void`  
- `public Make<T>() : T`  
- `public virtual ToBoolean(System.IFormatProvider provider) : System.Boolean`  
- `public virtual ToByte(System.IFormatProvider provider) : System.Byte`  
- `public virtual ToChar(System.IFormatProvider provider) : System.Char`  
- `public virtual ToDateTime(System.IFormatProvider provider) : System.DateTime`  
- `public virtual ToDecimal(System.IFormatProvider provider) : System.Decimal`  
- `public virtual ToDouble(System.IFormatProvider provider) : System.Double`  
- `public virtual ToInt16(System.IFormatProvider provider) : System.Int16`  
- `public virtual ToInt32(System.IFormatProvider provider) : System.Int32`  
- `public virtual ToInt64(System.IFormatProvider provider) : System.Int64`  
- `public ToJSON() : System.String`  
- `public ToJSON(Colossal.Json.EncodeOptions options) : System.String`  
- `public virtual ToSByte(System.IFormatProvider provider) : System.SByte`  
- `public virtual ToSingle(System.IFormatProvider provider) : System.Single`  
- `public virtual ToString(System.IFormatProvider provider) : System.String`  
- `public virtual ToString() : System.String`  
- `public virtual ToType(System.Type conversionType, System.IFormatProvider provider) : System.Object`  
- `public virtual ToUInt16(System.IFormatProvider provider) : System.UInt16`  
- `public virtual ToUInt32(System.IFormatProvider provider) : System.UInt32`  
- `public virtual ToUInt64(System.IFormatProvider provider) : System.UInt64`  
- `public virtual TryGet(System.String key) : Colossal.Json.Variant`  
- `public virtual TryGetValue(System.String key, Colossal.Json.Variant& variant) : System.Boolean`  
- `public Write<T>(T& item) : System.Void`  

