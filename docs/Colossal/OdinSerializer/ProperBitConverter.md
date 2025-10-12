# Colossal.OdinSerializer.ProperBitConverter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `private static readonly System.UInt32[] ByteToHexCharLookupLowerCase`  
- `private static readonly System.UInt32[] ByteToHexCharLookupUpperCase`  
- `private static readonly System.Byte[] HexToByteLookup`  

## Methods

- `public static BytesToHexString(System.Byte[] bytes, System.Boolean lowerCaseHexChars = True) : System.String`  
- `private static CreateByteToHexLookup(System.Boolean upperCase) : System.UInt32[]`  
- `public static GetBytes(System.Byte[] buffer, System.Int32 index, System.Int16 value) : System.Void`  
- `public static GetBytes(System.Byte[] buffer, System.Int32 index, System.UInt16 value) : System.Void`  
- `public static GetBytes(System.Byte[] buffer, System.Int32 index, System.Int32 value) : System.Void`  
- `public static GetBytes(System.Byte[] buffer, System.Int32 index, System.UInt32 value) : System.Void`  
- `public static GetBytes(System.Byte[] buffer, System.Int32 index, System.Int64 value) : System.Void`  
- `public static GetBytes(System.Byte[] buffer, System.Int32 index, System.UInt64 value) : System.Void`  
- `public static GetBytes(System.Byte[] buffer, System.Int32 index, System.Single value) : System.Void`  
- `public static GetBytes(System.Byte[] buffer, System.Int32 index, System.Double value) : System.Void`  
- `public static GetBytes(System.Byte[] buffer, System.Int32 index, System.Decimal value) : System.Void`  
- `public static GetBytes(System.Byte[] buffer, System.Int32 index, System.Guid value) : System.Void`  
- `public static HexStringToBytes(System.String hex) : System.Byte[]`  
- `public static ToDecimal(System.Byte[] buffer, System.Int32 index) : System.Decimal`  
- `public static ToDouble(System.Byte[] buffer, System.Int32 index) : System.Double`  
- `public static ToGuid(System.Byte[] buffer, System.Int32 index) : System.Guid`  
- `public static ToInt16(System.Byte[] buffer, System.Int32 index) : System.Int16`  
- `public static ToInt32(System.Byte[] buffer, System.Int32 index) : System.Int32`  
- `public static ToInt64(System.Byte[] buffer, System.Int32 index) : System.Int64`  
- `public static ToSingle(System.Byte[] buffer, System.Int32 index) : System.Single`  
- `public static ToUInt16(System.Byte[] buffer, System.Int32 index) : System.UInt16`  
- `public static ToUInt32(System.Byte[] buffer, System.Int32 index) : System.UInt32`  
- `public static ToUInt64(System.Byte[] buffer, System.Int32 index) : System.UInt64`  

## Nested types

- `Colossal.OdinSerializer.ProperBitConverter+SingleByteUnion`  
- `Colossal.OdinSerializer.ProperBitConverter+DoubleByteUnion`  
- `Colossal.OdinSerializer.ProperBitConverter+DecimalByteUnion`  
- `Colossal.OdinSerializer.ProperBitConverter+GuidByteUnion`  

