# Colossal.Mono.Cecil.IMetadataImporter

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IMetadataImporter
{
    public abstract Colossal.Mono.Cecil.AssemblyNameReference ImportReference(Colossal.Mono.Cecil.AssemblyNameReference reference);
    public abstract Colossal.Mono.Cecil.TypeReference ImportReference(Colossal.Mono.Cecil.TypeReference type, Colossal.Mono.Cecil.IGenericParameterProvider context);
    public abstract Colossal.Mono.Cecil.FieldReference ImportReference(Colossal.Mono.Cecil.FieldReference field, Colossal.Mono.Cecil.IGenericParameterProvider context);
    public abstract Colossal.Mono.Cecil.MethodReference ImportReference(Colossal.Mono.Cecil.MethodReference method, Colossal.Mono.Cecil.IGenericParameterProvider context);
}
```


## Methods

- `public abstract ImportReference(Colossal.Mono.Cecil.AssemblyNameReference reference) : Colossal.Mono.Cecil.AssemblyNameReference`  

```csharp
public abstract Colossal.Mono.Cecil.AssemblyNameReference ImportReference(Colossal.Mono.Cecil.AssemblyNameReference reference);
```

- `public abstract ImportReference(Colossal.Mono.Cecil.TypeReference type, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.TypeReference`  

```csharp
public abstract Colossal.Mono.Cecil.TypeReference ImportReference(Colossal.Mono.Cecil.TypeReference type, Colossal.Mono.Cecil.IGenericParameterProvider context);
```

- `public abstract ImportReference(Colossal.Mono.Cecil.FieldReference field, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.FieldReference`  

```csharp
public abstract Colossal.Mono.Cecil.FieldReference ImportReference(Colossal.Mono.Cecil.FieldReference field, Colossal.Mono.Cecil.IGenericParameterProvider context);
```

- `public abstract ImportReference(Colossal.Mono.Cecil.MethodReference method, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.MethodReference`  

```csharp
public abstract Colossal.Mono.Cecil.MethodReference ImportReference(Colossal.Mono.Cecil.MethodReference method, Colossal.Mono.Cecil.IGenericParameterProvider context);
```


