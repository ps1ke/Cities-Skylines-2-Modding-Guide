# Colossal.Mono.Cecil.IMethodSignature

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** interface abstract public  

**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Code

```csharp
public abstract interface IMethodSignature : Colossal.Mono.Cecil.IMetadataTokenProvider
{
    public System.Boolean HasThis { get; set; }
    public System.Boolean ExplicitThis { get; set; }
    public Colossal.Mono.Cecil.MethodCallingConvention CallingConvention { get; set; }
    public System.Boolean HasParameters { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ParameterDefinition> Parameters { get; }
    public Colossal.Mono.Cecil.TypeReference ReturnType { get; set; }
    public Colossal.Mono.Cecil.MethodReturnType MethodReturnType { get; }

}
```


## Properties

- `public System.Boolean HasThis { get; set }`  

```csharp
public System.Boolean HasThis { get; set; }
```

- `public System.Boolean ExplicitThis { get; set }`  

```csharp
public System.Boolean ExplicitThis { get; set; }
```

- `public Colossal.Mono.Cecil.MethodCallingConvention CallingConvention { get; set }`  

```csharp
public Colossal.Mono.Cecil.MethodCallingConvention CallingConvention { get; set; }
```

- `public System.Boolean HasParameters { get }`  

```csharp
public System.Boolean HasParameters { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ParameterDefinition> Parameters { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ParameterDefinition> Parameters { get; }
```

- `public Colossal.Mono.Cecil.TypeReference ReturnType { get; set }`  

```csharp
public Colossal.Mono.Cecil.TypeReference ReturnType { get; set; }
```

- `public Colossal.Mono.Cecil.MethodReturnType MethodReturnType { get }`  

```csharp
public Colossal.Mono.Cecil.MethodReturnType MethodReturnType { get; }
```


