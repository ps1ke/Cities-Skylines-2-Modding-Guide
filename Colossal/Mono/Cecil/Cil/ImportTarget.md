# Colossal.Mono.Cecil.Cil.ImportTarget

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `System.Object`  

## Code

```csharp
public sealed class ImportTarget
{
    internal Colossal.Mono.Cecil.Cil.ImportTargetKind kind;
    internal System.String namespace;
    internal Colossal.Mono.Cecil.TypeReference type;
    internal Colossal.Mono.Cecil.AssemblyNameReference reference;
    internal System.String alias;

    public System.String Namespace { get; set; }
    public Colossal.Mono.Cecil.TypeReference Type { get; set; }
    public Colossal.Mono.Cecil.AssemblyNameReference AssemblyReference { get; set; }
    public System.String Alias { get; set; }
    public Colossal.Mono.Cecil.Cil.ImportTargetKind Kind { get; set; }

    public ImportTarget(Colossal.Mono.Cecil.Cil.ImportTargetKind kind);

}
```


## Fields

- `internal Colossal.Mono.Cecil.Cil.ImportTargetKind kind`  

```csharp
internal Colossal.Mono.Cecil.Cil.ImportTargetKind kind;
```

- `internal System.String namespace`  

```csharp
internal System.String namespace;
```

- `internal Colossal.Mono.Cecil.TypeReference type`  

```csharp
internal Colossal.Mono.Cecil.TypeReference type;
```

- `internal Colossal.Mono.Cecil.AssemblyNameReference reference`  

```csharp
internal Colossal.Mono.Cecil.AssemblyNameReference reference;
```

- `internal System.String alias`  

```csharp
internal System.String alias;
```


## Properties

- `public System.String Namespace { get; set }`  

```csharp
public System.String Namespace { get; set; }
```

- `public Colossal.Mono.Cecil.TypeReference Type { get; set }`  

```csharp
public Colossal.Mono.Cecil.TypeReference Type { get; set; }
```

- `public Colossal.Mono.Cecil.AssemblyNameReference AssemblyReference { get; set }`  

```csharp
public Colossal.Mono.Cecil.AssemblyNameReference AssemblyReference { get; set; }
```

- `public System.String Alias { get; set }`  

```csharp
public System.String Alias { get; set; }
```

- `public Colossal.Mono.Cecil.Cil.ImportTargetKind Kind { get; set }`  

```csharp
public Colossal.Mono.Cecil.Cil.ImportTargetKind Kind { get; set; }
```


## Constructors

- `public ImportTarget(Colossal.Mono.Cecil.Cil.ImportTargetKind kind)`  

```csharp
public ImportTarget(Colossal.Mono.Cecil.Cil.ImportTargetKind kind);
```


