# Colossal.Mono.Cecil.DefaultMetadataImporter

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.IMetadataImporter`  

## Code

```csharp
public class DefaultMetadataImporter : Colossal.Mono.Cecil.IMetadataImporter
{
    protected readonly Colossal.Mono.Cecil.ModuleDefinition module;

    public DefaultMetadataImporter(Colossal.Mono.Cecil.ModuleDefinition module);

    private Colossal.Mono.Cecil.FieldReference ImportField(Colossal.Mono.Cecil.FieldReference field, Colossal.Mono.Cecil.ImportGenericContext context);
    private static System.Void ImportGenericParameters(Colossal.Mono.Cecil.IGenericParameterProvider imported, Colossal.Mono.Cecil.IGenericParameterProvider original);
    private Colossal.Mono.Cecil.MethodReference ImportMethod(Colossal.Mono.Cecil.MethodReference method, Colossal.Mono.Cecil.ImportGenericContext context);
    private Colossal.Mono.Cecil.MethodSpecification ImportMethodSpecification(Colossal.Mono.Cecil.MethodReference method, Colossal.Mono.Cecil.ImportGenericContext context);
    public virtual Colossal.Mono.Cecil.AssemblyNameReference ImportReference(Colossal.Mono.Cecil.AssemblyNameReference name);
    public virtual Colossal.Mono.Cecil.TypeReference ImportReference(Colossal.Mono.Cecil.TypeReference type, Colossal.Mono.Cecil.IGenericParameterProvider context);
    public virtual Colossal.Mono.Cecil.FieldReference ImportReference(Colossal.Mono.Cecil.FieldReference field, Colossal.Mono.Cecil.IGenericParameterProvider context);
    public virtual Colossal.Mono.Cecil.MethodReference ImportReference(Colossal.Mono.Cecil.MethodReference method, Colossal.Mono.Cecil.IGenericParameterProvider context);
    protected virtual Colossal.Mono.Cecil.IMetadataScope ImportScope(Colossal.Mono.Cecil.TypeReference type);
    protected Colossal.Mono.Cecil.IMetadataScope ImportScope(Colossal.Mono.Cecil.IMetadataScope scope);
    private Colossal.Mono.Cecil.TypeReference ImportType(Colossal.Mono.Cecil.TypeReference type, Colossal.Mono.Cecil.ImportGenericContext context);
    private Colossal.Mono.Cecil.TypeReference ImportTypeSpecification(Colossal.Mono.Cecil.TypeReference type, Colossal.Mono.Cecil.ImportGenericContext context);
}
```


## Fields

- `protected readonly Colossal.Mono.Cecil.ModuleDefinition module`  

```csharp
protected readonly Colossal.Mono.Cecil.ModuleDefinition module;
```


## Constructors

- `public DefaultMetadataImporter(Colossal.Mono.Cecil.ModuleDefinition module)`  

```csharp
public DefaultMetadataImporter(Colossal.Mono.Cecil.ModuleDefinition module);
```


## Methods

- `private ImportField(Colossal.Mono.Cecil.FieldReference field, Colossal.Mono.Cecil.ImportGenericContext context) : Colossal.Mono.Cecil.FieldReference`  

```csharp
private Colossal.Mono.Cecil.FieldReference ImportField(Colossal.Mono.Cecil.FieldReference field, Colossal.Mono.Cecil.ImportGenericContext context);
```

- `private static ImportGenericParameters(Colossal.Mono.Cecil.IGenericParameterProvider imported, Colossal.Mono.Cecil.IGenericParameterProvider original) : System.Void`  

```csharp
private static System.Void ImportGenericParameters(Colossal.Mono.Cecil.IGenericParameterProvider imported, Colossal.Mono.Cecil.IGenericParameterProvider original);
```

- `private ImportMethod(Colossal.Mono.Cecil.MethodReference method, Colossal.Mono.Cecil.ImportGenericContext context) : Colossal.Mono.Cecil.MethodReference`  

```csharp
private Colossal.Mono.Cecil.MethodReference ImportMethod(Colossal.Mono.Cecil.MethodReference method, Colossal.Mono.Cecil.ImportGenericContext context);
```

- `private ImportMethodSpecification(Colossal.Mono.Cecil.MethodReference method, Colossal.Mono.Cecil.ImportGenericContext context) : Colossal.Mono.Cecil.MethodSpecification`  

```csharp
private Colossal.Mono.Cecil.MethodSpecification ImportMethodSpecification(Colossal.Mono.Cecil.MethodReference method, Colossal.Mono.Cecil.ImportGenericContext context);
```

- `public virtual ImportReference(Colossal.Mono.Cecil.AssemblyNameReference name) : Colossal.Mono.Cecil.AssemblyNameReference`  

```csharp
public virtual Colossal.Mono.Cecil.AssemblyNameReference ImportReference(Colossal.Mono.Cecil.AssemblyNameReference name);
```

- `public virtual ImportReference(Colossal.Mono.Cecil.TypeReference type, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.TypeReference`  

```csharp
public virtual Colossal.Mono.Cecil.TypeReference ImportReference(Colossal.Mono.Cecil.TypeReference type, Colossal.Mono.Cecil.IGenericParameterProvider context);
```

- `public virtual ImportReference(Colossal.Mono.Cecil.FieldReference field, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.FieldReference`  

```csharp
public virtual Colossal.Mono.Cecil.FieldReference ImportReference(Colossal.Mono.Cecil.FieldReference field, Colossal.Mono.Cecil.IGenericParameterProvider context);
```

- `public virtual ImportReference(Colossal.Mono.Cecil.MethodReference method, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.MethodReference`  

```csharp
public virtual Colossal.Mono.Cecil.MethodReference ImportReference(Colossal.Mono.Cecil.MethodReference method, Colossal.Mono.Cecil.IGenericParameterProvider context);
```

- `protected virtual ImportScope(Colossal.Mono.Cecil.TypeReference type) : Colossal.Mono.Cecil.IMetadataScope`  

```csharp
protected virtual Colossal.Mono.Cecil.IMetadataScope ImportScope(Colossal.Mono.Cecil.TypeReference type);
```

- `protected ImportScope(Colossal.Mono.Cecil.IMetadataScope scope) : Colossal.Mono.Cecil.IMetadataScope`  

```csharp
protected Colossal.Mono.Cecil.IMetadataScope ImportScope(Colossal.Mono.Cecil.IMetadataScope scope);
```

- `private ImportType(Colossal.Mono.Cecil.TypeReference type, Colossal.Mono.Cecil.ImportGenericContext context) : Colossal.Mono.Cecil.TypeReference`  

```csharp
private Colossal.Mono.Cecil.TypeReference ImportType(Colossal.Mono.Cecil.TypeReference type, Colossal.Mono.Cecil.ImportGenericContext context);
```

- `private ImportTypeSpecification(Colossal.Mono.Cecil.TypeReference type, Colossal.Mono.Cecil.ImportGenericContext context) : Colossal.Mono.Cecil.TypeReference`  

```csharp
private Colossal.Mono.Cecil.TypeReference ImportTypeSpecification(Colossal.Mono.Cecil.TypeReference type, Colossal.Mono.Cecil.ImportGenericContext context);
```


