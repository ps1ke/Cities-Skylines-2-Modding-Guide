# Colossal.Mono.Cecil.MethodReturnType

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.IConstantProvider`, `Colossal.Mono.Cecil.IMetadataTokenProvider`, `Colossal.Mono.Cecil.ICustomAttributeProvider`, `Colossal.Mono.Cecil.IMarshalInfoProvider`  

## Code

```csharp
public sealed class MethodReturnType : Colossal.Mono.Cecil.IConstantProvider, Colossal.Mono.Cecil.IMetadataTokenProvider, Colossal.Mono.Cecil.ICustomAttributeProvider, Colossal.Mono.Cecil.IMarshalInfoProvider
{
    internal Colossal.Mono.Cecil.IMethodSignature method;
    internal Colossal.Mono.Cecil.ParameterDefinition parameter;
    private Colossal.Mono.Cecil.TypeReference return_type;

    public Colossal.Mono.Cecil.IMethodSignature Method { get; }
    public Colossal.Mono.Cecil.TypeReference ReturnType { get; set; }
    internal Colossal.Mono.Cecil.ParameterDefinition Parameter { internal get; }
    public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set; }
    public Colossal.Mono.Cecil.ParameterAttributes Attributes { get; set; }
    public System.String Name { get; set; }
    public System.Boolean HasCustomAttributes { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get; }
    public System.Boolean HasDefault { get; set; }
    public System.Boolean HasConstant { get; set; }
    public System.Object Constant { get; set; }
    public System.Boolean HasFieldMarshal { get; set; }
    public System.Boolean HasMarshalInfo { get; }
    public Colossal.Mono.Cecil.MarshalInfo MarshalInfo { get; set; }

    public MethodReturnType(Colossal.Mono.Cecil.IMethodSignature method);

}
```


## Fields

- `internal Colossal.Mono.Cecil.IMethodSignature method`  

```csharp
internal Colossal.Mono.Cecil.IMethodSignature method;
```

- `internal Colossal.Mono.Cecil.ParameterDefinition parameter`  

```csharp
internal Colossal.Mono.Cecil.ParameterDefinition parameter;
```

- `private Colossal.Mono.Cecil.TypeReference return_type`  

```csharp
private Colossal.Mono.Cecil.TypeReference return_type;
```


## Properties

- `public Colossal.Mono.Cecil.IMethodSignature Method { get }`  

```csharp
public Colossal.Mono.Cecil.IMethodSignature Method { get; }
```

- `public Colossal.Mono.Cecil.TypeReference ReturnType { get; set }`  

```csharp
public Colossal.Mono.Cecil.TypeReference ReturnType { get; set; }
```

- `internal Colossal.Mono.Cecil.ParameterDefinition Parameter { internal get }`  

```csharp
internal Colossal.Mono.Cecil.ParameterDefinition Parameter { internal get; }
```

- `public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set }`  

```csharp
public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set; }
```

- `public Colossal.Mono.Cecil.ParameterAttributes Attributes { get; set }`  

```csharp
public Colossal.Mono.Cecil.ParameterAttributes Attributes { get; set; }
```

- `public System.String Name { get; set }`  

```csharp
public System.String Name { get; set; }
```

- `public System.Boolean HasCustomAttributes { get }`  

```csharp
public System.Boolean HasCustomAttributes { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get; }
```

- `public System.Boolean HasDefault { get; set }`  

```csharp
public System.Boolean HasDefault { get; set; }
```

- `public System.Boolean HasConstant { get; set }`  

```csharp
public System.Boolean HasConstant { get; set; }
```

- `public System.Object Constant { get; set }`  

```csharp
public System.Object Constant { get; set; }
```

- `public System.Boolean HasFieldMarshal { get; set }`  

```csharp
public System.Boolean HasFieldMarshal { get; set; }
```

- `public System.Boolean HasMarshalInfo { get }`  

```csharp
public System.Boolean HasMarshalInfo { get; }
```

- `public Colossal.Mono.Cecil.MarshalInfo MarshalInfo { get; set }`  

```csharp
public Colossal.Mono.Cecil.MarshalInfo MarshalInfo { get; set; }
```


## Constructors

- `public MethodReturnType(Colossal.Mono.Cecil.IMethodSignature method)`  

```csharp
public MethodReturnType(Colossal.Mono.Cecil.IMethodSignature method);
```


