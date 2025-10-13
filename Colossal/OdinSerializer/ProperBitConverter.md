# Colossal.OdinSerializer.ProperBitConverter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ProperBitConverter
{
    private static readonly System.UInt32[] ByteToHexCharLookupLowerCase;
    private static readonly System.UInt32[] ByteToHexCharLookupUpperCase;
    private static readonly System.Byte[] HexToByteLookup;

    public static System.String BytesToHexString(System.Byte[] bytes, System.Boolean lowerCaseHexChars);
    private static System.UInt32[] CreateByteToHexLookup(System.Boolean upperCase);
    public static System.Void GetBytes(System.Byte[] buffer, System.Int32 index, System.Int16 value);
    public static System.Void GetBytes(System.Byte[] buffer, System.Int32 index, System.UInt16 value);
    public static System.Void GetBytes(System.Byte[] buffer, System.Int32 index, System.Int32 value);
    public static System.Void GetBytes(System.Byte[] buffer, System.Int32 index, System.UInt32 value);
    public static System.Void GetBytes(System.Byte[] buffer, System.Int32 index, System.Int64 value);
    public static System.Void GetBytes(System.Byte[] buffer, System.Int32 index, System.UInt64 value);
    public static System.Void GetBytes(System.Byte[] buffer, System.Int32 index, System.Single value);
    public static System.Void GetBytes(System.Byte[] buffer, System.Int32 index, System.Double value);
    public static System.Void GetBytes(System.Byte[] buffer, System.Int32 index, System.Decimal value);
    public static System.Void GetBytes(System.Byte[] buffer, System.Int32 index, System.Guid value);
    public static System.Byte[] HexStringToBytes(System.String hex);
    public static System.Decimal ToDecimal(System.Byte[] buffer, System.Int32 index);
    public static System.Double ToDouble(System.Byte[] buffer, System.Int32 index);
    public static System.Guid ToGuid(System.Byte[] buffer, System.Int32 index);
    public static System.Int16 ToInt16(System.Byte[] buffer, System.Int32 index);
    public static System.Int32 ToInt32(System.Byte[] buffer, System.Int32 index);
    public static System.Int64 ToInt64(System.Byte[] buffer, System.Int32 index);
    public static System.Single ToSingle(System.Byte[] buffer, System.Int32 index);
    public static System.UInt16 ToUInt16(System.Byte[] buffer, System.Int32 index);
    public static System.UInt32 ToUInt32(System.Byte[] buffer, System.Int32 index);
    public static System.UInt64 ToUInt64(System.Byte[] buffer, System.Int32 index);
}
```


## Fields

- `private static readonly System.UInt32[] ByteToHexCharLookupLowerCase`  

```csharp
private static readonly System.UInt32[] ByteToHexCharLookupLowerCase;
```

- `private static readonly System.UInt32[] ByteToHexCharLookupUpperCase`  

```csharp
private static readonly System.UInt32[] ByteToHexCharLookupUpperCase;
```

- `private static readonly System.Byte[] HexToByteLookup`  

```csharp
private static readonly System.Byte[] HexToByteLookup;
```


## Methods

- `public static BytesToHexString(System.Byte[] bytes, System.Boolean lowerCaseHexChars = True) : System.String`  

```csharp
public static System.String BytesToHexString(System.Byte[] bytes, System.Boolean lowerCaseHexChars);
```

- `private static CreateByteToHexLookup(System.Boolean upperCase) : System.UInt32[]`  

```csharp
private static System.UInt32[] CreateByteToHexLookup(System.Boolean upperCase);
```

- `public static GetBytes(System.Byte[] buffer, System.Int32 index, System.Int16 value) : System.Void`  

```csharp
public static System.Void GetBytes(System.Byte[] buffer, System.Int32 index, System.Int16 value);
```

- `public static GetBytes(System.Byte[] buffer, System.Int32 index, System.UInt16 value) : System.Void`  

```csharp
public static System.Void GetBytes(System.Byte[] buffer, System.Int32 index, System.UInt16 value);
```

- `public static GetBytes(System.Byte[] buffer, System.Int32 index, System.Int32 value) : System.Void`  

```csharp
public static System.Void GetBytes(System.Byte[] buffer, System.Int32 index, System.Int32 value);
```

- `public static GetBytes(System.Byte[] buffer, System.Int32 index, System.UInt32 value) : System.Void`  

```csharp
public static System.Void GetBytes(System.Byte[] buffer, System.Int32 index, System.UInt32 value);
```

- `public static GetBytes(System.Byte[] buffer, System.Int32 index, System.Int64 value) : System.Void`  

```csharp
public static System.Void GetBytes(System.Byte[] buffer, System.Int32 index, System.Int64 value);
```

- `public static GetBytes(System.Byte[] buffer, System.Int32 index, System.UInt64 value) : System.Void`  

```csharp
public static System.Void GetBytes(System.Byte[] buffer, System.Int32 index, System.UInt64 value);
```

- `public static GetBytes(System.Byte[] buffer, System.Int32 index, System.Single value) : System.Void`  

```csharp
public static System.Void GetBytes(System.Byte[] buffer, System.Int32 index, System.Single value);
```

- `public static GetBytes(System.Byte[] buffer, System.Int32 index, System.Double value) : System.Void`  

```csharp
public static System.Void GetBytes(System.Byte[] buffer, System.Int32 index, System.Double value);
```

- `public static GetBytes(System.Byte[] buffer, System.Int32 index, System.Decimal value) : System.Void`  

```csharp
public static System.Void GetBytes(System.Byte[] buffer, System.Int32 index, System.Decimal value);
```

- `public static GetBytes(System.Byte[] buffer, System.Int32 index, System.Guid value) : System.Void`  

```csharp
public static System.Void GetBytes(System.Byte[] buffer, System.Int32 index, System.Guid value);
```

- `public static HexStringToBytes(System.String hex) : System.Byte[]`  

```csharp
public static System.Byte[] HexStringToBytes(System.String hex);
```

- `public static ToDecimal(System.Byte[] buffer, System.Int32 index) : System.Decimal`  

```csharp
public static System.Decimal ToDecimal(System.Byte[] buffer, System.Int32 index);
```

- `public static ToDouble(System.Byte[] buffer, System.Int32 index) : System.Double`  

```csharp
public static System.Double ToDouble(System.Byte[] buffer, System.Int32 index);
```

- `public static ToGuid(System.Byte[] buffer, System.Int32 index) : System.Guid`  

```csharp
public static System.Guid ToGuid(System.Byte[] buffer, System.Int32 index);
```

- `public static ToInt16(System.Byte[] buffer, System.Int32 index) : System.Int16`  

```csharp
public static System.Int16 ToInt16(System.Byte[] buffer, System.Int32 index);
```

- `public static ToInt32(System.Byte[] buffer, System.Int32 index) : System.Int32`  

```csharp
public static System.Int32 ToInt32(System.Byte[] buffer, System.Int32 index);
```

- `public static ToInt64(System.Byte[] buffer, System.Int32 index) : System.Int64`  

```csharp
public static System.Int64 ToInt64(System.Byte[] buffer, System.Int32 index);
```

- `public static ToSingle(System.Byte[] buffer, System.Int32 index) : System.Single`  

```csharp
public static System.Single ToSingle(System.Byte[] buffer, System.Int32 index);
```

- `public static ToUInt16(System.Byte[] buffer, System.Int32 index) : System.UInt16`  

```csharp
public static System.UInt16 ToUInt16(System.Byte[] buffer, System.Int32 index);
```

- `public static ToUInt32(System.Byte[] buffer, System.Int32 index) : System.UInt32`  

```csharp
public static System.UInt32 ToUInt32(System.Byte[] buffer, System.Int32 index);
```

- `public static ToUInt64(System.Byte[] buffer, System.Int32 index) : System.UInt64`  

```csharp
public static System.UInt64 ToUInt64(System.Byte[] buffer, System.Int32 index);
```


## Nested types

- `Colossal.OdinSerializer.ProperBitConverter+SingleByteUnion`  
- `Colossal.OdinSerializer.ProperBitConverter+DoubleByteUnion`  
- `Colossal.OdinSerializer.ProperBitConverter+DecimalByteUnion`  
- `Colossal.OdinSerializer.ProperBitConverter+GuidByteUnion`  

