# Colossal.Mono.Cecil.IGenericParameterProvider

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** interface abstract public  

**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Code

```csharp
public abstract interface IGenericParameterProvider : Colossal.Mono.Cecil.IMetadataTokenProvider
{
    public System.Boolean HasGenericParameters { get; }
    public System.Boolean IsDefinition { get; }
    public Colossal.Mono.Cecil.ModuleDefinition Module { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.GenericParameter> GenericParameters { get; }
    public Colossal.Mono.Cecil.GenericParameterType GenericParameterType { get; }

}
```


## Properties

- `public System.Boolean HasGenericParameters { get }`  

```csharp
public System.Boolean HasGenericParameters { get; }
```

- `public System.Boolean IsDefinition { get }`  

```csharp
public System.Boolean IsDefinition { get; }
```

- `public Colossal.Mono.Cecil.ModuleDefinition Module { get }`  

```csharp
public Colossal.Mono.Cecil.ModuleDefinition Module { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.GenericParameter> GenericParameters { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.GenericParameter> GenericParameters { get; }
```

- `public Colossal.Mono.Cecil.GenericParameterType GenericParameterType { get }`  

```csharp
public Colossal.Mono.Cecil.GenericParameterType GenericParameterType { get; }
```


