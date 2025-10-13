# Colossal.Mono.Cecil.MethodReference

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class public  

**Base:** `Colossal.Mono.Cecil.MemberReference`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`, `Colossal.Mono.Cecil.IMethodSignature`, `Colossal.Mono.Cecil.IGenericParameterProvider`, `Colossal.Mono.Cecil.IGenericContext`  

## Code

```csharp
public class MethodReference : Colossal.Mono.Cecil.MemberReference, Colossal.Mono.Cecil.IMetadataTokenProvider, Colossal.Mono.Cecil.IMethodSignature, Colossal.Mono.Cecil.IGenericParameterProvider, Colossal.Mono.Cecil.IGenericContext
{
    internal Colossal.Mono.Cecil.ParameterDefinitionCollection parameters;
    private Colossal.Mono.Cecil.MethodReturnType return_type;
    private System.Boolean has_this;
    private System.Boolean explicit_this;
    private Colossal.Mono.Cecil.MethodCallingConvention calling_convention;
    internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.GenericParameter> generic_parameters;

    public System.Boolean HasThis { get; set; }
    public System.Boolean ExplicitThis { get; set; }
    public Colossal.Mono.Cecil.MethodCallingConvention CallingConvention { get; set; }
    public System.Boolean HasParameters { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ParameterDefinition> Parameters { get; }
    private Colossal.Mono.Cecil.IGenericParameterProvider Colossal.Mono.Cecil.IGenericContext.Type { private get; }
    private Colossal.Mono.Cecil.IGenericParameterProvider Colossal.Mono.Cecil.IGenericContext.Method { private get; }
    private Colossal.Mono.Cecil.GenericParameterType Colossal.Mono.Cecil.IGenericParameterProvider.GenericParameterType { private get; }
    public System.Boolean HasGenericParameters { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.GenericParameter> GenericParameters { get; }
    public Colossal.Mono.Cecil.TypeReference ReturnType { get; set; }
    public Colossal.Mono.Cecil.MethodReturnType MethodReturnType { get; set; }
    public System.String FullName { get; }
    public System.Boolean IsGenericInstance { get; }
    public System.Boolean ContainsGenericParameter { get; }

    internal MethodReference();
    public MethodReference(System.String name, Colossal.Mono.Cecil.TypeReference returnType);
    public MethodReference(System.String name, Colossal.Mono.Cecil.TypeReference returnType, Colossal.Mono.Cecil.TypeReference declaringType);

    public virtual Colossal.Mono.Cecil.MethodReference GetElementMethod();
    public virtual Colossal.Mono.Cecil.MethodDefinition Resolve();
    protected virtual Colossal.Mono.Cecil.IMemberDefinition ResolveDefinition();
}
```


## Fields

- `internal Colossal.Mono.Cecil.ParameterDefinitionCollection parameters`  

```csharp
internal Colossal.Mono.Cecil.ParameterDefinitionCollection parameters;
```

- `private Colossal.Mono.Cecil.MethodReturnType return_type`  

```csharp
private Colossal.Mono.Cecil.MethodReturnType return_type;
```

- `private System.Boolean has_this`  

```csharp
private System.Boolean has_this;
```

- `private System.Boolean explicit_this`  

```csharp
private System.Boolean explicit_this;
```

- `private Colossal.Mono.Cecil.MethodCallingConvention calling_convention`  

```csharp
private Colossal.Mono.Cecil.MethodCallingConvention calling_convention;
```

- `internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.GenericParameter> generic_parameters`  

```csharp
internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.GenericParameter> generic_parameters;
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

- `private Colossal.Mono.Cecil.IGenericParameterProvider Colossal.Mono.Cecil.IGenericContext.Type { private get }`  

```csharp
private Colossal.Mono.Cecil.IGenericParameterProvider Colossal.Mono.Cecil.IGenericContext.Type { private get; }
```

- `private Colossal.Mono.Cecil.IGenericParameterProvider Colossal.Mono.Cecil.IGenericContext.Method { private get }`  

```csharp
private Colossal.Mono.Cecil.IGenericParameterProvider Colossal.Mono.Cecil.IGenericContext.Method { private get; }
```

- `private Colossal.Mono.Cecil.GenericParameterType Colossal.Mono.Cecil.IGenericParameterProvider.GenericParameterType { private get }`  

```csharp
private Colossal.Mono.Cecil.GenericParameterType Colossal.Mono.Cecil.IGenericParameterProvider.GenericParameterType { private get; }
```

- `public System.Boolean HasGenericParameters { get }`  

```csharp
public System.Boolean HasGenericParameters { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.GenericParameter> GenericParameters { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.GenericParameter> GenericParameters { get; }
```

- `public Colossal.Mono.Cecil.TypeReference ReturnType { get; set }`  

```csharp
public Colossal.Mono.Cecil.TypeReference ReturnType { get; set; }
```

- `public Colossal.Mono.Cecil.MethodReturnType MethodReturnType { get; set }`  

```csharp
public Colossal.Mono.Cecil.MethodReturnType MethodReturnType { get; set; }
```

- `public System.String FullName { get }`  

```csharp
public System.String FullName { get; }
```

- `public System.Boolean IsGenericInstance { get }`  

```csharp
public System.Boolean IsGenericInstance { get; }
```

- `public System.Boolean ContainsGenericParameter { get }`  

```csharp
public System.Boolean ContainsGenericParameter { get; }
```


## Constructors

- `internal MethodReference()`  

```csharp
internal MethodReference();
```

- `public MethodReference(System.String name, Colossal.Mono.Cecil.TypeReference returnType)`  

```csharp
public MethodReference(System.String name, Colossal.Mono.Cecil.TypeReference returnType);
```

- `public MethodReference(System.String name, Colossal.Mono.Cecil.TypeReference returnType, Colossal.Mono.Cecil.TypeReference declaringType)`  

```csharp
public MethodReference(System.String name, Colossal.Mono.Cecil.TypeReference returnType, Colossal.Mono.Cecil.TypeReference declaringType);
```


## Methods

- `public virtual GetElementMethod() : Colossal.Mono.Cecil.MethodReference`  

```csharp
public virtual Colossal.Mono.Cecil.MethodReference GetElementMethod();
```

- `public virtual Resolve() : Colossal.Mono.Cecil.MethodDefinition`  

```csharp
public virtual Colossal.Mono.Cecil.MethodDefinition Resolve();
```

- `protected virtual ResolveDefinition() : Colossal.Mono.Cecil.IMemberDefinition`  

```csharp
protected virtual Colossal.Mono.Cecil.IMemberDefinition ResolveDefinition();
```


