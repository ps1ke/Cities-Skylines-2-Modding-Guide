# Colossal.Mono.Cecil.IReflectionImporter

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IReflectionImporter
{
    public abstract Colossal.Mono.Cecil.AssemblyNameReference ImportReference(System.Reflection.AssemblyName reference);
    public abstract Colossal.Mono.Cecil.TypeReference ImportReference(System.Type type, Colossal.Mono.Cecil.IGenericParameterProvider context);
    public abstract Colossal.Mono.Cecil.FieldReference ImportReference(System.Reflection.FieldInfo field, Colossal.Mono.Cecil.IGenericParameterProvider context);
    public abstract Colossal.Mono.Cecil.MethodReference ImportReference(System.Reflection.MethodBase method, Colossal.Mono.Cecil.IGenericParameterProvider context);
}
```


## Methods

- `public abstract ImportReference(System.Reflection.AssemblyName reference) : Colossal.Mono.Cecil.AssemblyNameReference`  

```csharp
public abstract Colossal.Mono.Cecil.AssemblyNameReference ImportReference(System.Reflection.AssemblyName reference);
```

- `public abstract ImportReference(System.Type type, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.TypeReference`  

```csharp
public abstract Colossal.Mono.Cecil.TypeReference ImportReference(System.Type type, Colossal.Mono.Cecil.IGenericParameterProvider context);
```

- `public abstract ImportReference(System.Reflection.FieldInfo field, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.FieldReference`  

```csharp
public abstract Colossal.Mono.Cecil.FieldReference ImportReference(System.Reflection.FieldInfo field, Colossal.Mono.Cecil.IGenericParameterProvider context);
```

- `public abstract ImportReference(System.Reflection.MethodBase method, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.MethodReference`  

```csharp
public abstract Colossal.Mono.Cecil.MethodReference ImportReference(System.Reflection.MethodBase method, Colossal.Mono.Cecil.IGenericParameterProvider context);
```


