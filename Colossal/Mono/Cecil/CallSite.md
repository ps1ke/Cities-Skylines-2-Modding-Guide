# Colossal.Mono.Cecil.CallSite

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.IMethodSignature`, `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Code

```csharp
public sealed class CallSite : Colossal.Mono.Cecil.IMethodSignature, Colossal.Mono.Cecil.IMetadataTokenProvider
{
    private readonly Colossal.Mono.Cecil.MethodReference signature;

    public System.Boolean HasThis { get; set; }
    public System.Boolean ExplicitThis { get; set; }
    public Colossal.Mono.Cecil.MethodCallingConvention CallingConvention { get; set; }
    public System.Boolean HasParameters { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ParameterDefinition> Parameters { get; }
    public Colossal.Mono.Cecil.TypeReference ReturnType { get; set; }
    public Colossal.Mono.Cecil.MethodReturnType MethodReturnType { get; }
    public System.String Name { get; set; }
    public System.String Namespace { get; set; }
    public Colossal.Mono.Cecil.ModuleDefinition Module { get; }
    public Colossal.Mono.Cecil.IMetadataScope Scope { get; }
    public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set; }
    public System.String FullName { get; }

    internal CallSite();
    public CallSite(Colossal.Mono.Cecil.TypeReference returnType);

    public virtual System.String ToString();
}
```


## Fields

- `private readonly Colossal.Mono.Cecil.MethodReference signature`  

```csharp
private readonly Colossal.Mono.Cecil.MethodReference signature;
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

- `public System.String Name { get; set }`  

```csharp
public System.String Name { get; set; }
```

- `public System.String Namespace { get; set }`  

```csharp
public System.String Namespace { get; set; }
```

- `public Colossal.Mono.Cecil.ModuleDefinition Module { get }`  

```csharp
public Colossal.Mono.Cecil.ModuleDefinition Module { get; }
```

- `public Colossal.Mono.Cecil.IMetadataScope Scope { get }`  

```csharp
public Colossal.Mono.Cecil.IMetadataScope Scope { get; }
```

- `public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set }`  

```csharp
public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set; }
```

- `public System.String FullName { get }`  

```csharp
public System.String FullName { get; }
```


## Constructors

- `internal CallSite()`  

```csharp
internal CallSite();
```

- `public CallSite(Colossal.Mono.Cecil.TypeReference returnType)`  

```csharp
public CallSite(Colossal.Mono.Cecil.TypeReference returnType);
```


## Methods

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


