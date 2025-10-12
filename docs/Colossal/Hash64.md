# Colossal.Hash64

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Colossal.Hash64>`, `System.IComparable<Colossal.Hash64>`  

## Fields

- `public Unity.Mathematics.uint2 value`  
- `private static readonly System.Char[] kHexToLiteral`  
- `private static readonly System.SByte[] kLiteralToHex`  
- `private static const System.Int32 kGUIDStringLength`  

## Properties

- `public System.Boolean isValid { get }`  

## Constructors

- `public Hash64(Unity.Mathematics.uint2 value)`  
- `public Hash64(System.UInt32 x, System.UInt32 y)`  
- `public Hash64(System.String value)`  

## Methods

- `public Calculate(System.Byte[] data) : System.Void`  
- `public Calculate(System.String data) : System.Void`  
- `public Calculate(System.Void* input, System.Int64 length) : System.Void`  
- `public Calculate<T>(T& data) : System.Void`  
- `public CompareTo(Colossal.Hash64 other) : System.Int32`  
- `public Equals(Colossal.Hash64 obj) : System.Boolean`  
- `public virtual Equals(System.Object obj) : System.Boolean`  
- `public virtual GetHashCode() : System.Int32`  
- `private GetResult(System.UInt32 me, System.UInt32 them) : System.Int32`  
- `private static StringToHash(System.Char* guidString, System.Int32 length) : Unity.Mathematics.uint2`  
- `public virtual ToString() : System.String`  

