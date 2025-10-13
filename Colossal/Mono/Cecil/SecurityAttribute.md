# Colossal.Mono.Cecil.SecurityAttribute

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.ICustomAttribute`  

**Attributes:** `DebuggerDisplay`  

## Code

```csharp
public sealed class SecurityAttribute : Colossal.Mono.Cecil.ICustomAttribute
{
    private Colossal.Mono.Cecil.TypeReference attribute_type;
    internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeNamedArgument> fields;
    internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeNamedArgument> properties;

    public Colossal.Mono.Cecil.TypeReference AttributeType { get; set; }
    public System.Boolean HasFields { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeNamedArgument> Fields { get; }
    public System.Boolean HasProperties { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeNamedArgument> Properties { get; }
    private System.Boolean Colossal.Mono.Cecil.ICustomAttribute.HasConstructorArguments { private get; }
    private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeArgument> Colossal.Mono.Cecil.ICustomAttribute.ConstructorArguments { private get; }

    public SecurityAttribute(Colossal.Mono.Cecil.TypeReference attributeType);

}
```


## Fields

- `private Colossal.Mono.Cecil.TypeReference attribute_type`  

```csharp
private Colossal.Mono.Cecil.TypeReference attribute_type;
```

- `internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeNamedArgument> fields`  

```csharp
internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeNamedArgument> fields;
```

- `internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeNamedArgument> properties`  

```csharp
internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeNamedArgument> properties;
```


## Properties

- `public Colossal.Mono.Cecil.TypeReference AttributeType { get; set }`  

```csharp
public Colossal.Mono.Cecil.TypeReference AttributeType { get; set; }
```

- `public System.Boolean HasFields { get }`  

```csharp
public System.Boolean HasFields { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeNamedArgument> Fields { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeNamedArgument> Fields { get; }
```

- `public System.Boolean HasProperties { get }`  

```csharp
public System.Boolean HasProperties { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeNamedArgument> Properties { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeNamedArgument> Properties { get; }
```

- `private System.Boolean Colossal.Mono.Cecil.ICustomAttribute.HasConstructorArguments { private get }`  

```csharp
private System.Boolean Colossal.Mono.Cecil.ICustomAttribute.HasConstructorArguments { private get; }
```

- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeArgument> Colossal.Mono.Cecil.ICustomAttribute.ConstructorArguments { private get }`  

```csharp
private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeArgument> Colossal.Mono.Cecil.ICustomAttribute.ConstructorArguments { private get; }
```


## Constructors

- `public SecurityAttribute(Colossal.Mono.Cecil.TypeReference attributeType)`  

```csharp
public SecurityAttribute(Colossal.Mono.Cecil.TypeReference attributeType);
```


