# Colossal.Hash128

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Colossal.Hash128>`, `System.IComparable<Colossal.Hash128>`  

## Fields

- `public Unity.Mathematics.uint4 value`  
- `public static readonly Colossal.Hash128 Empty`  
- `private static readonly System.Char[] kHexToLiteral`  
- `private static readonly System.SByte[] kLiteralToHex`  
- `public static const System.Int32 kGUIDStringLength`  
- `public static const System.Int32 kGUIDByteLength`  

## Properties

- `public System.Boolean isValid { get }`  

## Constructors

- `public Hash128(Unity.Mathematics.uint4 value)`  
- `public Hash128(System.UInt32 x, System.UInt32 y, System.UInt32 z, System.UInt32 w)`  
- `public Hash128(System.String value)`  
- `public Hash128(System.String value, System.Boolean guidFormatted)`  

## Methods

- `public Calculate(System.Byte[] data) : System.Void`  
- `public Calculate(System.String data) : System.Void`  
- `public Calculate(System.Void* input, System.Int64 length) : System.Void`  
- `public Calculate<T>(T& data) : System.Void`  
- `public CompareTo(Colossal.Hash128 other) : System.Int32`  
- `public static CreateGuid(System.String uniquePath) : Colossal.Hash128`  
- `public Equals(Colossal.Hash128 obj) : System.Boolean`  
- `public virtual Equals(System.Object obj) : System.Boolean`  
- `public virtual GetHashCode() : System.Int32`  
- `public static Parse(System.String value) : Colossal.Hash128`  
- `private static StringToHash(System.Char* guidString, System.Int32 length, System.Boolean guidFormatted = True) : Unity.Mathematics.uint4`  
- `public ToByteArray() : System.Byte[]`  
- `public virtual ToString() : System.String`  
- `public static TryParse(System.String value, Colossal.Hash128& hash) : System.Boolean`  

