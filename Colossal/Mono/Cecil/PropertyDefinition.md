# Colossal.Mono.Cecil.PropertyDefinition

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.PropertyReference`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`, `Colossal.Mono.Cecil.IMemberDefinition`, `Colossal.Mono.Cecil.ICustomAttributeProvider`, `Colossal.Mono.Cecil.IConstantProvider`  

## Code

```csharp
public sealed class PropertyDefinition : Colossal.Mono.Cecil.PropertyReference, Colossal.Mono.Cecil.IMetadataTokenProvider, Colossal.Mono.Cecil.IMemberDefinition, Colossal.Mono.Cecil.ICustomAttributeProvider, Colossal.Mono.Cecil.IConstantProvider
{
    private System.Nullable<System.Boolean> has_this;
    private System.UInt16 attributes;
    private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> custom_attributes;
    internal Colossal.Mono.Cecil.MethodDefinition get_method;
    internal Colossal.Mono.Cecil.MethodDefinition set_method;
    internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodDefinition> other_methods;
    private System.Object constant;

    public Colossal.Mono.Cecil.PropertyAttributes Attributes { get; set; }
    public System.Boolean HasThis { get; set; }
    public System.Boolean HasCustomAttributes { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get; }
    public Colossal.Mono.Cecil.MethodDefinition GetMethod { get; set; }
    public Colossal.Mono.Cecil.MethodDefinition SetMethod { get; set; }
    public System.Boolean HasOtherMethods { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodDefinition> OtherMethods { get; }
    public System.Boolean HasParameters { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ParameterDefinition> Parameters { get; }
    public System.Boolean HasConstant { get; set; }
    public System.Object Constant { get; set; }
    public System.Boolean IsSpecialName { get; set; }
    public System.Boolean IsRuntimeSpecialName { get; set; }
    public System.Boolean HasDefault { get; set; }
    public Colossal.Mono.Cecil.TypeDefinition DeclaringType { get; set; }
    public System.Boolean IsDefinition { get; }
    public System.String FullName { get; }

    public PropertyDefinition(System.String name, Colossal.Mono.Cecil.PropertyAttributes attributes, Colossal.Mono.Cecil.TypeReference propertyType);

    private System.Void InitializeMethods();
    private static Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ParameterDefinition> MirrorParameters(Colossal.Mono.Cecil.MethodDefinition method, System.Int32 bound);
    public virtual Colossal.Mono.Cecil.PropertyDefinition Resolve();
}
```


## Fields

- `private System.Nullable<System.Boolean> has_this`  

```csharp
private System.Nullable<System.Boolean> has_this;
```

- `private System.UInt16 attributes`  

```csharp
private System.UInt16 attributes;
```

- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> custom_attributes`  

```csharp
private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> custom_attributes;
```

- `internal Colossal.Mono.Cecil.MethodDefinition get_method`  

```csharp
internal Colossal.Mono.Cecil.MethodDefinition get_method;
```

- `internal Colossal.Mono.Cecil.MethodDefinition set_method`  

```csharp
internal Colossal.Mono.Cecil.MethodDefinition set_method;
```

- `internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodDefinition> other_methods`  

```csharp
internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodDefinition> other_methods;
```

- `private System.Object constant`  

```csharp
private System.Object constant;
```


## Properties

- `public Colossal.Mono.Cecil.PropertyAttributes Attributes { get; set }`  

```csharp
public Colossal.Mono.Cecil.PropertyAttributes Attributes { get; set; }
```

- `public System.Boolean HasThis { get; set }`  

```csharp
public System.Boolean HasThis { get; set; }
```

- `public System.Boolean HasCustomAttributes { get }`  

```csharp
public System.Boolean HasCustomAttributes { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get; }
```

- `public Colossal.Mono.Cecil.MethodDefinition GetMethod { get; set }`  

```csharp
public Colossal.Mono.Cecil.MethodDefinition GetMethod { get; set; }
```

- `public Colossal.Mono.Cecil.MethodDefinition SetMethod { get; set }`  

```csharp
public Colossal.Mono.Cecil.MethodDefinition SetMethod { get; set; }
```

- `public System.Boolean HasOtherMethods { get }`  

```csharp
public System.Boolean HasOtherMethods { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodDefinition> OtherMethods { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodDefinition> OtherMethods { get; }
```

- `public System.Boolean HasParameters { get }`  

```csharp
public System.Boolean HasParameters { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ParameterDefinition> Parameters { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ParameterDefinition> Parameters { get; }
```

- `public System.Boolean HasConstant { get; set }`  

```csharp
public System.Boolean HasConstant { get; set; }
```

- `public System.Object Constant { get; set }`  

```csharp
public System.Object Constant { get; set; }
```

- `public System.Boolean IsSpecialName { get; set }`  

```csharp
public System.Boolean IsSpecialName { get; set; }
```

- `public System.Boolean IsRuntimeSpecialName { get; set }`  

```csharp
public System.Boolean IsRuntimeSpecialName { get; set; }
```

- `public System.Boolean HasDefault { get; set }`  

```csharp
public System.Boolean HasDefault { get; set; }
```

- `public Colossal.Mono.Cecil.TypeDefinition DeclaringType { get; set }`  

```csharp
public Colossal.Mono.Cecil.TypeDefinition DeclaringType { get; set; }
```

- `public System.Boolean IsDefinition { get }`  

```csharp
public System.Boolean IsDefinition { get; }
```

- `public System.String FullName { get }`  

```csharp
public System.String FullName { get; }
```


## Constructors

- `public PropertyDefinition(System.String name, Colossal.Mono.Cecil.PropertyAttributes attributes, Colossal.Mono.Cecil.TypeReference propertyType)`  

```csharp
public PropertyDefinition(System.String name, Colossal.Mono.Cecil.PropertyAttributes attributes, Colossal.Mono.Cecil.TypeReference propertyType);
```


## Methods

- `private InitializeMethods() : System.Void`  

```csharp
private System.Void InitializeMethods();
```

- `private static MirrorParameters(Colossal.Mono.Cecil.MethodDefinition method, System.Int32 bound) : Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ParameterDefinition>`  

```csharp
private static Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ParameterDefinition> MirrorParameters(Colossal.Mono.Cecil.MethodDefinition method, System.Int32 bound);
```

- `public virtual Resolve() : Colossal.Mono.Cecil.PropertyDefinition`  

```csharp
public virtual Colossal.Mono.Cecil.PropertyDefinition Resolve();
```


## Nested types

- `Colossal.Mono.Cecil.PropertyDefinition+<>c`  

