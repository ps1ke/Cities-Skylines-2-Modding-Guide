# Colossal.Hash64

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Colossal.Hash64>`, `System.IComparable<Colossal.Hash64>`  

## Code

```csharp
public sealed struct Hash64 : System.IEquatable<Colossal.Hash64>, System.IComparable<Colossal.Hash64>
{
    public Unity.Mathematics.uint2 value;
    private static readonly System.Char[] kHexToLiteral;
    private static readonly System.SByte[] kLiteralToHex;
    private static const System.Int32 kGUIDStringLength;

    public System.Boolean isValid { get; }

    public Hash64(Unity.Mathematics.uint2 value);
    public Hash64(System.UInt32 x, System.UInt32 y);
    public Hash64(System.String value);

    public System.Void Calculate(System.Byte[] data);
    public System.Void Calculate(System.String data);
    public System.Void Calculate(System.Void* input, System.Int64 length);
    public System.Void Calculate<T>(T& data);
    public System.Int32 CompareTo(Colossal.Hash64 other);
    public System.Boolean Equals(Colossal.Hash64 obj);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
    private System.Int32 GetResult(System.UInt32 me, System.UInt32 them);
    private static Unity.Mathematics.uint2 StringToHash(System.Char* guidString, System.Int32 length);
    public virtual System.String ToString();
}
```


## Fields

- `public Unity.Mathematics.uint2 value`  

```csharp
public Unity.Mathematics.uint2 value;
```

- `private static readonly System.Char[] kHexToLiteral`  

```csharp
private static readonly System.Char[] kHexToLiteral;
```

- `private static readonly System.SByte[] kLiteralToHex`  

```csharp
private static readonly System.SByte[] kLiteralToHex;
```

- `private static const System.Int32 kGUIDStringLength`  

```csharp
private static const System.Int32 kGUIDStringLength;
```


## Properties

- `public System.Boolean isValid { get }`  

```csharp
public System.Boolean isValid { get; }
```


## Constructors

- `public Hash64(Unity.Mathematics.uint2 value)`  

```csharp
public Hash64(Unity.Mathematics.uint2 value);
```

- `public Hash64(System.UInt32 x, System.UInt32 y)`  

```csharp
public Hash64(System.UInt32 x, System.UInt32 y);
```

- `public Hash64(System.String value)`  

```csharp
public Hash64(System.String value);
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

- `public CompareTo(Colossal.Hash64 other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Colossal.Hash64 other);
```

- `public Equals(Colossal.Hash64 obj) : System.Boolean`  

```csharp
public System.Boolean Equals(Colossal.Hash64 obj);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `private GetResult(System.UInt32 me, System.UInt32 them) : System.Int32`  

```csharp
private System.Int32 GetResult(System.UInt32 me, System.UInt32 them);
```

- `private static StringToHash(System.Char* guidString, System.Int32 length) : Unity.Mathematics.uint2`  

```csharp
private static Unity.Mathematics.uint2 StringToHash(System.Char* guidString, System.Int32 length);
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


