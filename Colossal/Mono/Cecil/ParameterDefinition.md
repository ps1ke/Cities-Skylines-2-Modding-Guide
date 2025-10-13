# Colossal.Mono.Cecil.ParameterDefinition

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.ParameterReference`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`, `Colossal.Mono.Cecil.ICustomAttributeProvider`, `Colossal.Mono.Cecil.IConstantProvider`, `Colossal.Mono.Cecil.IMarshalInfoProvider`  

## Code

```csharp
public sealed class ParameterDefinition : Colossal.Mono.Cecil.ParameterReference, Colossal.Mono.Cecil.IMetadataTokenProvider, Colossal.Mono.Cecil.ICustomAttributeProvider, Colossal.Mono.Cecil.IConstantProvider, Colossal.Mono.Cecil.IMarshalInfoProvider
{
    private System.UInt16 attributes;
    internal Colossal.Mono.Cecil.IMethodSignature method;
    private System.Object constant;
    private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> custom_attributes;
    private Colossal.Mono.Cecil.MarshalInfo marshal_info;

    public Colossal.Mono.Cecil.ParameterAttributes Attributes { get; set; }
    public Colossal.Mono.Cecil.IMethodSignature Method { get; }
    public System.Int32 Sequence { get; }
    public System.Boolean HasConstant { get; set; }
    public System.Object Constant { get; set; }
    public System.Boolean HasCustomAttributes { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get; }
    public System.Boolean HasMarshalInfo { get; }
    public Colossal.Mono.Cecil.MarshalInfo MarshalInfo { get; set; }
    public System.Boolean IsIn { get; set; }
    public System.Boolean IsOut { get; set; }
    public System.Boolean IsLcid { get; set; }
    public System.Boolean IsReturnValue { get; set; }
    public System.Boolean IsOptional { get; set; }
    public System.Boolean HasDefault { get; set; }
    public System.Boolean HasFieldMarshal { get; set; }

    internal ParameterDefinition(Colossal.Mono.Cecil.TypeReference parameterType, Colossal.Mono.Cecil.IMethodSignature method);
    public ParameterDefinition(Colossal.Mono.Cecil.TypeReference parameterType);
    public ParameterDefinition(System.String name, Colossal.Mono.Cecil.ParameterAttributes attributes, Colossal.Mono.Cecil.TypeReference parameterType);

    public virtual Colossal.Mono.Cecil.ParameterDefinition Resolve();
}
```


## Fields

- `private System.UInt16 attributes`  

```csharp
private System.UInt16 attributes;
```

- `internal Colossal.Mono.Cecil.IMethodSignature method`  

```csharp
internal Colossal.Mono.Cecil.IMethodSignature method;
```

- `private System.Object constant`  

```csharp
private System.Object constant;
```

- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> custom_attributes`  

```csharp
private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> custom_attributes;
```

- `private Colossal.Mono.Cecil.MarshalInfo marshal_info`  

```csharp
private Colossal.Mono.Cecil.MarshalInfo marshal_info;
```


## Properties

- `public Colossal.Mono.Cecil.ParameterAttributes Attributes { get; set }`  

```csharp
public Colossal.Mono.Cecil.ParameterAttributes Attributes { get; set; }
```

- `public Colossal.Mono.Cecil.IMethodSignature Method { get }`  

```csharp
public Colossal.Mono.Cecil.IMethodSignature Method { get; }
```

- `public System.Int32 Sequence { get }`  

```csharp
public System.Int32 Sequence { get; }
```

- `public System.Boolean HasConstant { get; set }`  

```csharp
public System.Boolean HasConstant { get; set; }
```

- `public System.Object Constant { get; set }`  

```csharp
public System.Object Constant { get; set; }
```

- `public System.Boolean HasCustomAttributes { get }`  

```csharp
public System.Boolean HasCustomAttributes { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get; }
```

- `public System.Boolean HasMarshalInfo { get }`  

```csharp
public System.Boolean HasMarshalInfo { get; }
```

- `public Colossal.Mono.Cecil.MarshalInfo MarshalInfo { get; set }`  

```csharp
public Colossal.Mono.Cecil.MarshalInfo MarshalInfo { get; set; }
```

- `public System.Boolean IsIn { get; set }`  

```csharp
public System.Boolean IsIn { get; set; }
```

- `public System.Boolean IsOut { get; set }`  

```csharp
public System.Boolean IsOut { get; set; }
```

- `public System.Boolean IsLcid { get; set }`  

```csharp
public System.Boolean IsLcid { get; set; }
```

- `public System.Boolean IsReturnValue { get; set }`  

```csharp
public System.Boolean IsReturnValue { get; set; }
```

- `public System.Boolean IsOptional { get; set }`  

```csharp
public System.Boolean IsOptional { get; set; }
```

- `public System.Boolean HasDefault { get; set }`  

```csharp
public System.Boolean HasDefault { get; set; }
```

- `public System.Boolean HasFieldMarshal { get; set }`  

```csharp
public System.Boolean HasFieldMarshal { get; set; }
```


## Constructors

- `internal ParameterDefinition(Colossal.Mono.Cecil.TypeReference parameterType, Colossal.Mono.Cecil.IMethodSignature method)`  

```csharp
internal ParameterDefinition(Colossal.Mono.Cecil.TypeReference parameterType, Colossal.Mono.Cecil.IMethodSignature method);
```

- `public ParameterDefinition(Colossal.Mono.Cecil.TypeReference parameterType)`  

```csharp
public ParameterDefinition(Colossal.Mono.Cecil.TypeReference parameterType);
```

- `public ParameterDefinition(System.String name, Colossal.Mono.Cecil.ParameterAttributes attributes, Colossal.Mono.Cecil.TypeReference parameterType)`  

```csharp
public ParameterDefinition(System.String name, Colossal.Mono.Cecil.ParameterAttributes attributes, Colossal.Mono.Cecil.TypeReference parameterType);
```


## Methods

- `public virtual Resolve() : Colossal.Mono.Cecil.ParameterDefinition`  

```csharp
public virtual Colossal.Mono.Cecil.ParameterDefinition Resolve();
```


