# Colossal.Mono.Cecil.IMemberDefinition

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** interface abstract public  

**Implements:** `Colossal.Mono.Cecil.ICustomAttributeProvider`, `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Code

```csharp
public abstract interface IMemberDefinition : Colossal.Mono.Cecil.ICustomAttributeProvider, Colossal.Mono.Cecil.IMetadataTokenProvider
{
    public System.String Name { get; set; }
    public System.String FullName { get; }
    public System.Boolean IsSpecialName { get; set; }
    public System.Boolean IsRuntimeSpecialName { get; set; }
    public Colossal.Mono.Cecil.TypeDefinition DeclaringType { get; set; }

}
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

- `public System.Boolean IsSpecialName { get; set }`  

```csharp
public System.Boolean IsSpecialName { get; set; }
```

- `public System.Boolean IsRuntimeSpecialName { get; set }`  

```csharp
public System.Boolean IsRuntimeSpecialName { get; set; }
```

- `public Colossal.Mono.Cecil.TypeDefinition DeclaringType { get; set }`  

```csharp
public Colossal.Mono.Cecil.TypeDefinition DeclaringType { get; set; }
```


