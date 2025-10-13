# Colossal.Mono.Cecil.ModuleReference

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.IMetadataScope`, `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Code

```csharp
public class ModuleReference : Colossal.Mono.Cecil.IMetadataScope, Colossal.Mono.Cecil.IMetadataTokenProvider
{
    private System.String name;
    internal Colossal.Mono.Cecil.MetadataToken token;

    public System.String Name { get; set; }
    public Colossal.Mono.Cecil.MetadataScopeType MetadataScopeType { get; }
    public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set; }

    internal ModuleReference();
    public ModuleReference(System.String name);

    public virtual System.String ToString();
}
```


## Fields

- `private System.String name`  

```csharp
private System.String name;
```

- `internal Colossal.Mono.Cecil.MetadataToken token`  

```csharp
internal Colossal.Mono.Cecil.MetadataToken token;
```


## Properties

- `public System.String Name { get; set }`  

```csharp
public System.String Name { get; set; }
```

- `public Colossal.Mono.Cecil.MetadataScopeType MetadataScopeType { get }`  

```csharp
public Colossal.Mono.Cecil.MetadataScopeType MetadataScopeType { get; }
```

- `public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set }`  

```csharp
public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set; }
```


## Constructors

- `internal ModuleReference()`  

```csharp
internal ModuleReference();
```

- `public ModuleReference(System.String name)`  

```csharp
public ModuleReference(System.String name);
```


## Methods

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


