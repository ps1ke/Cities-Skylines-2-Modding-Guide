# Colossal.Mono.Cecil.LinkedResource

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.Resource`  

## Code

```csharp
public sealed class LinkedResource : Colossal.Mono.Cecil.Resource
{
    internal System.Byte[] hash;
    private System.String file;

    public System.Byte[] Hash { get; }
    public System.String File { get; set; }
    public Colossal.Mono.Cecil.ResourceType ResourceType { get; }

    public LinkedResource(System.String name, Colossal.Mono.Cecil.ManifestResourceAttributes flags);
    public LinkedResource(System.String name, Colossal.Mono.Cecil.ManifestResourceAttributes flags, System.String file);

}
```


## Fields

- `internal System.Byte[] hash`  

```csharp
internal System.Byte[] hash;
```

- `private System.String file`  

```csharp
private System.String file;
```


## Properties

- `public System.Byte[] Hash { get }`  

```csharp
public System.Byte[] Hash { get; }
```

- `public System.String File { get; set }`  

```csharp
public System.String File { get; set; }
```

- `public Colossal.Mono.Cecil.ResourceType ResourceType { get }`  

```csharp
public Colossal.Mono.Cecil.ResourceType ResourceType { get; }
```


## Constructors

- `public LinkedResource(System.String name, Colossal.Mono.Cecil.ManifestResourceAttributes flags)`  

```csharp
public LinkedResource(System.String name, Colossal.Mono.Cecil.ManifestResourceAttributes flags);
```

- `public LinkedResource(System.String name, Colossal.Mono.Cecil.ManifestResourceAttributes flags, System.String file)`  

```csharp
public LinkedResource(System.String name, Colossal.Mono.Cecil.ManifestResourceAttributes flags, System.String file);
```


