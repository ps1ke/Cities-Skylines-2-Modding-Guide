# Colossal.Mono.Cecil.MetadataToken

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Colossal.Mono.Cecil.MetadataToken>`  

## Code

```csharp
public sealed struct MetadataToken : System.IEquatable<Colossal.Mono.Cecil.MetadataToken>
{
    private readonly System.UInt32 token;
    public static readonly Colossal.Mono.Cecil.MetadataToken Zero;

    public System.UInt32 RID { get; }
    public Colossal.Mono.Cecil.TokenType TokenType { get; }

    public MetadataToken(System.UInt32 token);
    public MetadataToken(Colossal.Mono.Cecil.TokenType type);
    public MetadataToken(Colossal.Mono.Cecil.TokenType type, System.UInt32 rid);
    public MetadataToken(Colossal.Mono.Cecil.TokenType type, System.Int32 rid);

    public System.Boolean Equals(Colossal.Mono.Cecil.MetadataToken other);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
    public System.Int32 ToInt32();
    public virtual System.String ToString();
    public System.UInt32 ToUInt32();
}
```


## Fields

- `private readonly System.UInt32 token`  

```csharp
private readonly System.UInt32 token;
```

- `public static readonly Colossal.Mono.Cecil.MetadataToken Zero`  

```csharp
public static readonly Colossal.Mono.Cecil.MetadataToken Zero;
```


## Properties

- `public System.UInt32 RID { get }`  

```csharp
public System.UInt32 RID { get; }
```

- `public Colossal.Mono.Cecil.TokenType TokenType { get }`  

```csharp
public Colossal.Mono.Cecil.TokenType TokenType { get; }
```


## Constructors

- `public MetadataToken(System.UInt32 token)`  

```csharp
public MetadataToken(System.UInt32 token);
```

- `public MetadataToken(Colossal.Mono.Cecil.TokenType type)`  

```csharp
public MetadataToken(Colossal.Mono.Cecil.TokenType type);
```

- `public MetadataToken(Colossal.Mono.Cecil.TokenType type, System.UInt32 rid)`  

```csharp
public MetadataToken(Colossal.Mono.Cecil.TokenType type, System.UInt32 rid);
```

- `public MetadataToken(Colossal.Mono.Cecil.TokenType type, System.Int32 rid)`  

```csharp
public MetadataToken(Colossal.Mono.Cecil.TokenType type, System.Int32 rid);
```


## Methods

- `public Equals(Colossal.Mono.Cecil.MetadataToken other) : System.Boolean`  

```csharp
public System.Boolean Equals(Colossal.Mono.Cecil.MetadataToken other);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public ToInt32() : System.Int32`  

```csharp
public System.Int32 ToInt32();
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```

- `public ToUInt32() : System.UInt32`  

```csharp
public System.UInt32 ToUInt32();
```


