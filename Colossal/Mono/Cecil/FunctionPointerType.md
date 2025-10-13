# Colossal.Mono.Cecil.FunctionPointerType

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.TypeSpecification`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`, `Colossal.Mono.Cecil.IGenericParameterProvider`, `Colossal.Mono.Cecil.IGenericContext`, `Colossal.Mono.Cecil.IMethodSignature`  

## Code

```csharp
public sealed class FunctionPointerType : Colossal.Mono.Cecil.TypeSpecification, Colossal.Mono.Cecil.IMetadataTokenProvider, Colossal.Mono.Cecil.IGenericParameterProvider, Colossal.Mono.Cecil.IGenericContext, Colossal.Mono.Cecil.IMethodSignature
{
    private readonly Colossal.Mono.Cecil.MethodReference function;

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
    public Colossal.Mono.Cecil.IMetadataScope Scope { get; set; }
    public System.Boolean IsFunctionPointer { get; }
    public System.Boolean ContainsGenericParameter { get; }
    public System.String FullName { get; }

    public FunctionPointerType();

    public virtual Colossal.Mono.Cecil.TypeReference GetElementType();
    public virtual Colossal.Mono.Cecil.TypeDefinition Resolve();
}
```


## Fields

- `private readonly Colossal.Mono.Cecil.MethodReference function`  

```csharp
private readonly Colossal.Mono.Cecil.MethodReference function;
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

- `public Colossal.Mono.Cecil.IMetadataScope Scope { get; set }`  

```csharp
public Colossal.Mono.Cecil.IMetadataScope Scope { get; set; }
```

- `public System.Boolean IsFunctionPointer { get }`  

```csharp
public System.Boolean IsFunctionPointer { get; }
```

- `public System.Boolean ContainsGenericParameter { get }`  

```csharp
public System.Boolean ContainsGenericParameter { get; }
```

- `public System.String FullName { get }`  

```csharp
public System.String FullName { get; }
```


## Constructors

- `public FunctionPointerType()`  

```csharp
public FunctionPointerType();
```


## Methods

- `public virtual GetElementType() : Colossal.Mono.Cecil.TypeReference`  

```csharp
public virtual Colossal.Mono.Cecil.TypeReference GetElementType();
```

- `public virtual Resolve() : Colossal.Mono.Cecil.TypeDefinition`  

```csharp
public virtual Colossal.Mono.Cecil.TypeDefinition Resolve();
```


