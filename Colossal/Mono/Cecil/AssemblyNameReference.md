# Colossal.Mono.Cecil.AssemblyNameReference

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.IMetadataScope`, `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Code

```csharp
public class AssemblyNameReference : Colossal.Mono.Cecil.IMetadataScope, Colossal.Mono.Cecil.IMetadataTokenProvider
{
    private System.String name;
    private System.String culture;
    private System.Version version;
    private System.UInt32 attributes;
    private System.Byte[] public_key;
    private System.Byte[] public_key_token;
    private Colossal.Mono.Cecil.AssemblyHashAlgorithm hash_algorithm;
    private System.Byte[] hash;
    internal Colossal.Mono.Cecil.MetadataToken token;
    private System.String full_name;

    public System.String Name { get; set; }
    public System.String Culture { get; set; }
    public System.Version Version { get; set; }
    public Colossal.Mono.Cecil.AssemblyAttributes Attributes { get; set; }
    public System.Boolean HasPublicKey { get; set; }
    public System.Boolean IsSideBySideCompatible { get; set; }
    public System.Boolean IsRetargetable { get; set; }
    public System.Boolean IsWindowsRuntime { get; set; }
    public System.Byte[] PublicKey { get; set; }
    public System.Byte[] PublicKeyToken { get; set; }
    public Colossal.Mono.Cecil.MetadataScopeType MetadataScopeType { get; }
    public System.String FullName { get; }
    public Colossal.Mono.Cecil.AssemblyHashAlgorithm HashAlgorithm { get; set; }
    public System.Byte[] Hash { get; set; }
    public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set; }

    internal AssemblyNameReference();
    public AssemblyNameReference(System.String name, System.Version version);

    private System.Byte[] HashPublicKey();
    public static Colossal.Mono.Cecil.AssemblyNameReference Parse(System.String fullName);
    public virtual System.String ToString();
}
```


## Fields

- `private System.String name`  

```csharp
private System.String name;
```

- `private System.String culture`  

```csharp
private System.String culture;
```

- `private System.Version version`  

```csharp
private System.Version version;
```

- `private System.UInt32 attributes`  

```csharp
private System.UInt32 attributes;
```

- `private System.Byte[] public_key`  

```csharp
private System.Byte[] public_key;
```

- `private System.Byte[] public_key_token`  

```csharp
private System.Byte[] public_key_token;
```

- `private Colossal.Mono.Cecil.AssemblyHashAlgorithm hash_algorithm`  

```csharp
private Colossal.Mono.Cecil.AssemblyHashAlgorithm hash_algorithm;
```

- `private System.Byte[] hash`  

```csharp
private System.Byte[] hash;
```

- `internal Colossal.Mono.Cecil.MetadataToken token`  

```csharp
internal Colossal.Mono.Cecil.MetadataToken token;
```

- `private System.String full_name`  

```csharp
private System.String full_name;
```


## Properties

- `public System.String Name { get; set }`  

```csharp
public System.String Name { get; set; }
```

- `public System.String Culture { get; set }`  

```csharp
public System.String Culture { get; set; }
```

- `public System.Version Version { get; set }`  

```csharp
public System.Version Version { get; set; }
```

- `public Colossal.Mono.Cecil.AssemblyAttributes Attributes { get; set }`  

```csharp
public Colossal.Mono.Cecil.AssemblyAttributes Attributes { get; set; }
```

- `public System.Boolean HasPublicKey { get; set }`  

```csharp
public System.Boolean HasPublicKey { get; set; }
```

- `public System.Boolean IsSideBySideCompatible { get; set }`  

```csharp
public System.Boolean IsSideBySideCompatible { get; set; }
```

- `public System.Boolean IsRetargetable { get; set }`  

```csharp
public System.Boolean IsRetargetable { get; set; }
```

- `public System.Boolean IsWindowsRuntime { get; set }`  

```csharp
public System.Boolean IsWindowsRuntime { get; set; }
```

- `public System.Byte[] PublicKey { get; set }`  

```csharp
public System.Byte[] PublicKey { get; set; }
```

- `public System.Byte[] PublicKeyToken { get; set }`  

```csharp
public System.Byte[] PublicKeyToken { get; set; }
```

- `public Colossal.Mono.Cecil.MetadataScopeType MetadataScopeType { get }`  

```csharp
public Colossal.Mono.Cecil.MetadataScopeType MetadataScopeType { get; }
```

- `public System.String FullName { get }`  

```csharp
public System.String FullName { get; }
```

- `public Colossal.Mono.Cecil.AssemblyHashAlgorithm HashAlgorithm { get; set }`  

```csharp
public Colossal.Mono.Cecil.AssemblyHashAlgorithm HashAlgorithm { get; set; }
```

- `public System.Byte[] Hash { get; set }`  

```csharp
public System.Byte[] Hash { get; set; }
```

- `public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set }`  

```csharp
public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set; }
```


## Constructors

- `internal AssemblyNameReference()`  

```csharp
internal AssemblyNameReference();
```

- `public AssemblyNameReference(System.String name, System.Version version)`  

```csharp
public AssemblyNameReference(System.String name, System.Version version);
```


## Methods

- `private HashPublicKey() : System.Byte[]`  

```csharp
private System.Byte[] HashPublicKey();
```

- `public static Parse(System.String fullName) : Colossal.Mono.Cecil.AssemblyNameReference`  

```csharp
public static Colossal.Mono.Cecil.AssemblyNameReference Parse(System.String fullName);
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


