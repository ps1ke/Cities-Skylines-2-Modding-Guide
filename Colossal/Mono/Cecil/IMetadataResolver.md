# Colossal.Mono.Cecil.IMetadataResolver

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IMetadataResolver
{
    public abstract Colossal.Mono.Cecil.TypeDefinition Resolve(Colossal.Mono.Cecil.TypeReference type);
    public abstract Colossal.Mono.Cecil.FieldDefinition Resolve(Colossal.Mono.Cecil.FieldReference field);
    public abstract Colossal.Mono.Cecil.MethodDefinition Resolve(Colossal.Mono.Cecil.MethodReference method);
}
```


## Methods

- `public abstract Resolve(Colossal.Mono.Cecil.TypeReference type) : Colossal.Mono.Cecil.TypeDefinition`  

```csharp
public abstract Colossal.Mono.Cecil.TypeDefinition Resolve(Colossal.Mono.Cecil.TypeReference type);
```

- `public abstract Resolve(Colossal.Mono.Cecil.FieldReference field) : Colossal.Mono.Cecil.FieldDefinition`  

```csharp
public abstract Colossal.Mono.Cecil.FieldDefinition Resolve(Colossal.Mono.Cecil.FieldReference field);
```

- `public abstract Resolve(Colossal.Mono.Cecil.MethodReference method) : Colossal.Mono.Cecil.MethodDefinition`  

```csharp
public abstract Colossal.Mono.Cecil.MethodDefinition Resolve(Colossal.Mono.Cecil.MethodReference method);
```


