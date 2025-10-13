# Colossal.Hash128

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Colossal.Hash128>`, `System.IComparable<Colossal.Hash128>`  

## Code

```csharp
public sealed struct Hash128 : System.IEquatable<Colossal.Hash128>, System.IComparable<Colossal.Hash128>
{
    public Unity.Mathematics.uint4 value;
    public static readonly Colossal.Hash128 Empty;
    private static readonly System.Char[] kHexToLiteral;
    private static readonly System.SByte[] kLiteralToHex;
    public static const System.Int32 kGUIDStringLength;
    public static const System.Int32 kGUIDByteLength;

    public System.Boolean isValid { get; }

    public Hash128(Unity.Mathematics.uint4 value);
    public Hash128(System.UInt32 x, System.UInt32 y, System.UInt32 z, System.UInt32 w);
    public Hash128(System.String value);
    public Hash128(System.String value, System.Boolean guidFormatted);

    public System.Void Calculate(System.Byte[] data);
    public System.Void Calculate(System.String data);
    public System.Void Calculate(System.Void* input, System.Int64 length);
    public System.Void Calculate<T>(T& data);
    public System.Int32 CompareTo(Colossal.Hash128 other);
    public static Colossal.Hash128 CreateGuid(System.String uniquePath);
    public System.Boolean Equals(Colossal.Hash128 obj);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
    public static Colossal.Hash128 Parse(System.String value);
    private static Unity.Mathematics.uint4 StringToHash(System.Char* guidString, System.Int32 length, System.Boolean guidFormatted);
    public System.Byte[] ToByteArray();
    public virtual System.String ToString();
    public static System.Boolean TryParse(System.String value, Colossal.Hash128& hash);
}
```


## Fields

- `public Unity.Mathematics.uint4 value`  

```csharp
public Unity.Mathematics.uint4 value;
```

- `public static readonly Colossal.Hash128 Empty`  

```csharp
public static readonly Colossal.Hash128 Empty;
```

- `private static readonly System.Char[] kHexToLiteral`  

```csharp
private static readonly System.Char[] kHexToLiteral;
```

- `private static readonly System.SByte[] kLiteralToHex`  

```csharp
private static readonly System.SByte[] kLiteralToHex;
```

- `public static const System.Int32 kGUIDStringLength`  

```csharp
public static const System.Int32 kGUIDStringLength;
```

- `public static const System.Int32 kGUIDByteLength`  

```csharp
public static const System.Int32 kGUIDByteLength;
```


## Properties

- `public System.Boolean isValid { get }`  

```csharp
public System.Boolean isValid { get; }
```


## Constructors

- `public Hash128(Unity.Mathematics.uint4 value)`  

```csharp
public Hash128(Unity.Mathematics.uint4 value);
```

- `public Hash128(System.UInt32 x, System.UInt32 y, System.UInt32 z, System.UInt32 w)`  

```csharp
public Hash128(System.UInt32 x, System.UInt32 y, System.UInt32 z, System.UInt32 w);
```

- `public Hash128(System.String value)`  

```csharp
public Hash128(System.String value);
```

- `public Hash128(System.String value, System.Boolean guidFormatted)`  

```csharp
public Hash128(System.String value, System.Boolean guidFormatted);
```


## Methods

- `public Calculate(System.Byte[] data) : System.Void`  

```csharp
public System.Void Calculate(System.Byte[] data);
```

- `public Calculate(System.String data) : System.Void`  

```csharp
public System.Void Calculate(System.String data);
```

- `public Calculate(System.Void* input, System.Int64 length) : System.Void`  

```csharp
public System.Void Calculate(System.Void* input, System.Int64 length);
```

- `public Calculate<T>(T& data) : System.Void`  

```csharp
public System.Void Calculate<T>(T& data);
```

- `public CompareTo(Colossal.Hash128 other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Colossal.Hash128 other);
```

- `public static CreateGuid(System.String uniquePath) : Colossal.Hash128`  

```csharp
public static Colossal.Hash128 CreateGuid(System.String uniquePath);
```

- `public Equals(Colossal.Hash128 obj) : System.Boolean`  

```csharp
public System.Boolean Equals(Colossal.Hash128 obj);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public static Parse(System.String value) : Colossal.Hash128`  

```csharp
public static Colossal.Hash128 Parse(System.String value);
```

- `private static StringToHash(System.Char* guidString, System.Int32 length, System.Boolean guidFormatted = True) : Unity.Mathematics.uint4`  

```csharp
private static Unity.Mathematics.uint4 StringToHash(System.Char* guidString, System.Int32 length, System.Boolean guidFormatted);
```

- `public ToByteArray() : System.Byte[]`  

```csharp
public System.Byte[] ToByteArray();
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```

- `public static TryParse(System.String value, Colossal.Hash128& hash) : System.Boolean`  

```csharp
public static System.Boolean TryParse(System.String value, Colossal.Hash128& hash);
```


