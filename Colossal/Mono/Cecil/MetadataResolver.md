# Colossal.Mono.Cecil.MetadataResolver

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.IMetadataResolver`  

## Code

```csharp
public class MetadataResolver : Colossal.Mono.Cecil.IMetadataResolver
{
    private readonly Colossal.Mono.Cecil.IAssemblyResolver assembly_resolver;

    public Colossal.Mono.Cecil.IAssemblyResolver AssemblyResolver { get; }

    public MetadataResolver(Colossal.Mono.Cecil.IAssemblyResolver assemblyResolver);

    private static System.Boolean AreSame(Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ParameterDefinition> a, Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ParameterDefinition> b);
    private static System.Boolean AreSame(Colossal.Mono.Cecil.TypeSpecification a, Colossal.Mono.Cecil.TypeSpecification b);
    private static System.Boolean AreSame(Colossal.Mono.Cecil.ArrayType a, Colossal.Mono.Cecil.ArrayType b);
    private static System.Boolean AreSame(Colossal.Mono.Cecil.IModifierType a, Colossal.Mono.Cecil.IModifierType b);
    private static System.Boolean AreSame(Colossal.Mono.Cecil.GenericInstanceType a, Colossal.Mono.Cecil.GenericInstanceType b);
    private static System.Boolean AreSame(Colossal.Mono.Cecil.GenericParameter a, Colossal.Mono.Cecil.GenericParameter b);
    private static System.Boolean AreSame(Colossal.Mono.Cecil.TypeReference a, Colossal.Mono.Cecil.TypeReference b);
    private Colossal.Mono.Cecil.FieldDefinition GetField(Colossal.Mono.Cecil.TypeDefinition type, Colossal.Mono.Cecil.FieldReference reference);
    private static Colossal.Mono.Cecil.FieldDefinition GetField(Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.FieldDefinition> fields, Colossal.Mono.Cecil.FieldReference reference);
    private Colossal.Mono.Cecil.MethodDefinition GetMethod(Colossal.Mono.Cecil.TypeDefinition type, Colossal.Mono.Cecil.MethodReference reference);
    public static Colossal.Mono.Cecil.MethodDefinition GetMethod(Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodDefinition> methods, Colossal.Mono.Cecil.MethodReference reference);
    private static Colossal.Mono.Cecil.TypeDefinition GetType(Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.Cecil.TypeReference reference);
    private static Colossal.Mono.Cecil.TypeDefinition GetTypeDefinition(Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.Cecil.TypeReference type);
    private static System.Boolean IsVarArgCallTo(Colossal.Mono.Cecil.MethodDefinition method, Colossal.Mono.Cecil.MethodReference reference);
    public virtual Colossal.Mono.Cecil.TypeDefinition Resolve(Colossal.Mono.Cecil.TypeReference type);
    public virtual Colossal.Mono.Cecil.FieldDefinition Resolve(Colossal.Mono.Cecil.FieldReference field);
    public virtual Colossal.Mono.Cecil.MethodDefinition Resolve(Colossal.Mono.Cecil.MethodReference method);
}
```


## Fields

- `private readonly Colossal.Mono.Cecil.IAssemblyResolver assembly_resolver`  

```csharp
private readonly Colossal.Mono.Cecil.IAssemblyResolver assembly_resolver;
```


## Properties

- `public Colossal.Mono.Cecil.IAssemblyResolver AssemblyResolver { get }`  

```csharp
public Colossal.Mono.Cecil.IAssemblyResolver AssemblyResolver { get; }
```


## Constructors

- `public MetadataResolver(Colossal.Mono.Cecil.IAssemblyResolver assemblyResolver)`  

```csharp
public MetadataResolver(Colossal.Mono.Cecil.IAssemblyResolver assemblyResolver);
```


## Methods

- `private static AreSame(Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ParameterDefinition> a, Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ParameterDefinition> b) : System.Boolean`  

```csharp
private static System.Boolean AreSame(Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ParameterDefinition> a, Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ParameterDefinition> b);
```

- `private static AreSame(Colossal.Mono.Cecil.TypeSpecification a, Colossal.Mono.Cecil.TypeSpecification b) : System.Boolean`  

```csharp
private static System.Boolean AreSame(Colossal.Mono.Cecil.TypeSpecification a, Colossal.Mono.Cecil.TypeSpecification b);
```

- `private static AreSame(Colossal.Mono.Cecil.ArrayType a, Colossal.Mono.Cecil.ArrayType b) : System.Boolean`  

```csharp
private static System.Boolean AreSame(Colossal.Mono.Cecil.ArrayType a, Colossal.Mono.Cecil.ArrayType b);
```

- `private static AreSame(Colossal.Mono.Cecil.IModifierType a, Colossal.Mono.Cecil.IModifierType b) : System.Boolean`  

```csharp
private static System.Boolean AreSame(Colossal.Mono.Cecil.IModifierType a, Colossal.Mono.Cecil.IModifierType b);
```

- `private static AreSame(Colossal.Mono.Cecil.GenericInstanceType a, Colossal.Mono.Cecil.GenericInstanceType b) : System.Boolean`  

```csharp
private static System.Boolean AreSame(Colossal.Mono.Cecil.GenericInstanceType a, Colossal.Mono.Cecil.GenericInstanceType b);
```

- `private static AreSame(Colossal.Mono.Cecil.GenericParameter a, Colossal.Mono.Cecil.GenericParameter b) : System.Boolean`  

```csharp
private static System.Boolean AreSame(Colossal.Mono.Cecil.GenericParameter a, Colossal.Mono.Cecil.GenericParameter b);
```

- `private static AreSame(Colossal.Mono.Cecil.TypeReference a, Colossal.Mono.Cecil.TypeReference b) : System.Boolean`  

```csharp
private static System.Boolean AreSame(Colossal.Mono.Cecil.TypeReference a, Colossal.Mono.Cecil.TypeReference b);
```

- `private GetField(Colossal.Mono.Cecil.TypeDefinition type, Colossal.Mono.Cecil.FieldReference reference) : Colossal.Mono.Cecil.FieldDefinition`  

```csharp
private Colossal.Mono.Cecil.FieldDefinition GetField(Colossal.Mono.Cecil.TypeDefinition type, Colossal.Mono.Cecil.FieldReference reference);
```

- `private static GetField(Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.FieldDefinition> fields, Colossal.Mono.Cecil.FieldReference reference) : Colossal.Mono.Cecil.FieldDefinition`  

```csharp
private static Colossal.Mono.Cecil.FieldDefinition GetField(Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.FieldDefinition> fields, Colossal.Mono.Cecil.FieldReference reference);
```

- `private GetMethod(Colossal.Mono.Cecil.TypeDefinition type, Colossal.Mono.Cecil.MethodReference reference) : Colossal.Mono.Cecil.MethodDefinition`  

```csharp
private Colossal.Mono.Cecil.MethodDefinition GetMethod(Colossal.Mono.Cecil.TypeDefinition type, Colossal.Mono.Cecil.MethodReference reference);
```

- `public static GetMethod(Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodDefinition> methods, Colossal.Mono.Cecil.MethodReference reference) : Colossal.Mono.Cecil.MethodDefinition`  

```csharp
public static Colossal.Mono.Cecil.MethodDefinition GetMethod(Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodDefinition> methods, Colossal.Mono.Cecil.MethodReference reference);
```

- `private static GetType(Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.Cecil.TypeReference reference) : Colossal.Mono.Cecil.TypeDefinition`  

```csharp
private static Colossal.Mono.Cecil.TypeDefinition GetType(Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.Cecil.TypeReference reference);
```

- `private static GetTypeDefinition(Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.Cecil.TypeReference type) : Colossal.Mono.Cecil.TypeDefinition`  

```csharp
private static Colossal.Mono.Cecil.TypeDefinition GetTypeDefinition(Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.Cecil.TypeReference type);
```

- `private static IsVarArgCallTo(Colossal.Mono.Cecil.MethodDefinition method, Colossal.Mono.Cecil.MethodReference reference) : System.Boolean`  

```csharp
private static System.Boolean IsVarArgCallTo(Colossal.Mono.Cecil.MethodDefinition method, Colossal.Mono.Cecil.MethodReference reference);
```

- `public virtual Resolve(Colossal.Mono.Cecil.TypeReference type) : Colossal.Mono.Cecil.TypeDefinition`  

```csharp
public virtual Colossal.Mono.Cecil.TypeDefinition Resolve(Colossal.Mono.Cecil.TypeReference type);
```

- `public virtual Resolve(Colossal.Mono.Cecil.FieldReference field) : Colossal.Mono.Cecil.FieldDefinition`  

```csharp
public virtual Colossal.Mono.Cecil.FieldDefinition Resolve(Colossal.Mono.Cecil.FieldReference field);
```

- `public virtual Resolve(Colossal.Mono.Cecil.MethodReference method) : Colossal.Mono.Cecil.MethodDefinition`  

```csharp
public virtual Colossal.Mono.Cecil.MethodDefinition Resolve(Colossal.Mono.Cecil.MethodReference method);
```


