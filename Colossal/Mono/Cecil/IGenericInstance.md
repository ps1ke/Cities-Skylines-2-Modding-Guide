# Colossal.Mono.Cecil.IGenericInstance

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** interface abstract public  

**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Code

```csharp
public abstract interface IGenericInstance : Colossal.Mono.Cecil.IMetadataTokenProvider
{
    public System.Boolean HasGenericArguments { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.TypeReference> GenericArguments { get; }

}
```


## Properties

- `public System.Boolean HasGenericArguments { get }`  

```csharp
public System.Boolean HasGenericArguments { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.TypeReference> GenericArguments { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.TypeReference> GenericArguments { get; }
```


