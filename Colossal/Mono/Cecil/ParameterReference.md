# Colossal.Mono.Cecil.ParameterReference

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Code

```csharp
public abstract class ParameterReference : Colossal.Mono.Cecil.IMetadataTokenProvider
{
    private System.String name;
    internal System.Int32 index;
    protected Colossal.Mono.Cecil.TypeReference parameter_type;
    internal Colossal.Mono.Cecil.MetadataToken token;

    public System.String Name { get; set; }
    public System.Int32 Index { get; }
    public Colossal.Mono.Cecil.TypeReference ParameterType { get; set; }
    public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set; }

    internal ParameterReference(System.String name, Colossal.Mono.Cecil.TypeReference parameterType);

    public abstract Colossal.Mono.Cecil.ParameterDefinition Resolve();
    public virtual System.String ToString();
}
```


## Fields

- `private System.String name`  

```csharp
private System.String name;
```

- `internal System.Int32 index`  

```csharp
internal System.Int32 index;
```

- `protected Colossal.Mono.Cecil.TypeReference parameter_type`  

```csharp
protected Colossal.Mono.Cecil.TypeReference parameter_type;
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

- `public System.Int32 Index { get }`  

```csharp
public System.Int32 Index { get; }
```

- `public Colossal.Mono.Cecil.TypeReference ParameterType { get; set }`  

```csharp
public Colossal.Mono.Cecil.TypeReference ParameterType { get; set; }
```

- `public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set }`  

```csharp
public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set; }
```


## Constructors

- `internal ParameterReference(System.String name, Colossal.Mono.Cecil.TypeReference parameterType)`  

```csharp
internal ParameterReference(System.String name, Colossal.Mono.Cecil.TypeReference parameterType);
```


## Methods

- `public abstract Resolve() : Colossal.Mono.Cecil.ParameterDefinition`  

```csharp
public abstract Colossal.Mono.Cecil.ParameterDefinition Resolve();
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


