# Colossal.Mono.Cecil.MemberReference

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Code

```csharp
public abstract class MemberReference : Colossal.Mono.Cecil.IMetadataTokenProvider
{
    private System.String name;
    private Colossal.Mono.Cecil.TypeReference declaring_type;
    internal Colossal.Mono.Cecil.MetadataToken token;
    internal System.Object projection;

    public System.String Name { get; set; }
    public System.String FullName { get; }
    public Colossal.Mono.Cecil.TypeReference DeclaringType { get; set; }
    public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set; }
    public System.Boolean IsWindowsRuntimeProjection { get; }
    internal System.Boolean HasImage { internal get; }
    public Colossal.Mono.Cecil.ModuleDefinition Module { get; }
    public System.Boolean IsDefinition { get; }
    public System.Boolean ContainsGenericParameter { get; }

    internal MemberReference();
    internal MemberReference(System.String name);

    internal System.String MemberFullName();
    public Colossal.Mono.Cecil.IMemberDefinition Resolve();
    protected abstract Colossal.Mono.Cecil.IMemberDefinition ResolveDefinition();
    public virtual System.String ToString();
}
```


## Fields

- `private System.String name`  

```csharp
private System.String name;
```

- `private Colossal.Mono.Cecil.TypeReference declaring_type`  

```csharp
private Colossal.Mono.Cecil.TypeReference declaring_type;
```

- `internal Colossal.Mono.Cecil.MetadataToken token`  

```csharp
internal Colossal.Mono.Cecil.MetadataToken token;
```

- `internal System.Object projection`  

```csharp
internal System.Object projection;
```


## Properties

- `public System.String Name { get; set }`  

```csharp
public System.String Name { get; set; }
```

- `public System.String FullName { get }`  

```csharp
public System.String FullName { get; }
```

- `public Colossal.Mono.Cecil.TypeReference DeclaringType { get; set }`  

```csharp
public Colossal.Mono.Cecil.TypeReference DeclaringType { get; set; }
```

- `public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set }`  

```csharp
public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set; }
```

- `public System.Boolean IsWindowsRuntimeProjection { get }`  

```csharp
public System.Boolean IsWindowsRuntimeProjection { get; }
```

- `internal System.Boolean HasImage { internal get }`  

```csharp
internal System.Boolean HasImage { internal get; }
```

- `public Colossal.Mono.Cecil.ModuleDefinition Module { get }`  

```csharp
public Colossal.Mono.Cecil.ModuleDefinition Module { get; }
```

- `public System.Boolean IsDefinition { get }`  

```csharp
public System.Boolean IsDefinition { get; }
```

- `public System.Boolean ContainsGenericParameter { get }`  

```csharp
public System.Boolean ContainsGenericParameter { get; }
```


## Constructors

- `internal MemberReference()`  

```csharp
internal MemberReference();
```

- `internal MemberReference(System.String name)`  

```csharp
internal MemberReference(System.String name);
```


## Methods

- `internal MemberFullName() : System.String`  

```csharp
internal System.String MemberFullName();
```

- `public Resolve() : Colossal.Mono.Cecil.IMemberDefinition`  

```csharp
public Colossal.Mono.Cecil.IMemberDefinition Resolve();
```

- `protected abstract ResolveDefinition() : Colossal.Mono.Cecil.IMemberDefinition`  

```csharp
protected abstract Colossal.Mono.Cecil.IMemberDefinition ResolveDefinition();
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


