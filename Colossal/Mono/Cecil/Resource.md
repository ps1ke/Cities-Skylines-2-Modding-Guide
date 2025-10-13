# Colossal.Mono.Cecil.Resource

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class abstract public  

**Base:** `System.Object`  

## Code

```csharp
public abstract class Resource
{
    private System.String name;
    private System.UInt32 attributes;

    public System.String Name { get; set; }
    public Colossal.Mono.Cecil.ManifestResourceAttributes Attributes { get; set; }
    public Colossal.Mono.Cecil.ResourceType ResourceType { get; }
    public System.Boolean IsPublic { get; set; }
    public System.Boolean IsPrivate { get; set; }

    internal Resource(System.String name, Colossal.Mono.Cecil.ManifestResourceAttributes attributes);

}
```


## Fields

- `private System.String name`  

```csharp
private System.String name;
```

- `private System.UInt32 attributes`  

```csharp
private System.UInt32 attributes;
```


## Properties

- `public System.String Name { get; set }`  

```csharp
public System.String Name { get; set; }
```

- `public Colossal.Mono.Cecil.ManifestResourceAttributes Attributes { get; set }`  

```csharp
public Colossal.Mono.Cecil.ManifestResourceAttributes Attributes { get; set; }
```

- `public Colossal.Mono.Cecil.ResourceType ResourceType { get }`  

```csharp
public Colossal.Mono.Cecil.ResourceType ResourceType { get; }
```

- `public System.Boolean IsPublic { get; set }`  

```csharp
public System.Boolean IsPublic { get; set; }
```

- `public System.Boolean IsPrivate { get; set }`  

```csharp
public System.Boolean IsPrivate { get; set; }
```


## Constructors

- `internal Resource(System.String name, Colossal.Mono.Cecil.ManifestResourceAttributes attributes)`  

```csharp
internal Resource(System.String name, Colossal.Mono.Cecil.ManifestResourceAttributes attributes);
```


