# Colossal.Mono.Cecil.IMetadataScope

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** interface abstract public  

**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Code

```csharp
public abstract interface IMetadataScope : Colossal.Mono.Cecil.IMetadataTokenProvider
{
    public Colossal.Mono.Cecil.MetadataScopeType MetadataScopeType { get; }
    public System.String Name { get; set; }

}
```


## Properties

- `public Colossal.Mono.Cecil.MetadataScopeType MetadataScopeType { get }`  

```csharp
public Colossal.Mono.Cecil.MetadataScopeType MetadataScopeType { get; }
```

- `public System.String Name { get; set }`  

```csharp
public System.String Name { get; set; }
```


