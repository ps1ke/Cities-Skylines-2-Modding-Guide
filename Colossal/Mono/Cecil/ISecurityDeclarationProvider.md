# Colossal.Mono.Cecil.ISecurityDeclarationProvider

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** interface abstract public  

**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Code

```csharp
public abstract interface ISecurityDeclarationProvider : Colossal.Mono.Cecil.IMetadataTokenProvider
{
    public System.Boolean HasSecurityDeclarations { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.SecurityDeclaration> SecurityDeclarations { get; }

}
```


## Properties

- `public System.Boolean HasSecurityDeclarations { get }`  

```csharp
public System.Boolean HasSecurityDeclarations { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.SecurityDeclaration> SecurityDeclarations { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.SecurityDeclaration> SecurityDeclarations { get; }
```


