# Colossal.Mono.Cecil.CustomAttribute

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.ICustomAttribute`  

**Attributes:** `DebuggerDisplay`  

## Code

```csharp
public sealed class CustomAttribute : Colossal.Mono.Cecil.ICustomAttribute
{
    internal Colossal.Mono.Cecil.CustomAttributeValueProjection projection;
    internal readonly System.UInt32 signature;
    internal System.Boolean resolved;
    private Colossal.Mono.Cecil.MethodReference constructor;
    private System.Byte[] blob;
    internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeArgument> arguments;
    internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeNamedArgument> fields;
    internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeNamedArgument> properties;

    public Colossal.Mono.Cecil.MethodReference Constructor { get; set; }
    public Colossal.Mono.Cecil.TypeReference AttributeType { get; }
    public System.Boolean IsResolved { get; }
    public System.Boolean HasConstructorArguments { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeArgument> ConstructorArguments { get; }
    public System.Boolean HasFields { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeNamedArgument> Fields { get; }
    public System.Boolean HasProperties { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeNamedArgument> Properties { get; }
    internal System.Boolean HasImage { internal get; }
    internal Colossal.Mono.Cecil.ModuleDefinition Module { internal get; }

    internal CustomAttribute(System.UInt32 signature, Colossal.Mono.Cecil.MethodReference constructor);
    public CustomAttribute(Colossal.Mono.Cecil.MethodReference constructor);
    public CustomAttribute(Colossal.Mono.Cecil.MethodReference constructor, System.Byte[] blob);

    private System.Void <Resolve>b__35_0(Colossal.Mono.Cecil.CustomAttribute attribute, Colossal.Mono.Cecil.MetadataReader reader);
    public System.Byte[] GetBlob();
    private System.Void Resolve();
}
```


## Fields

- `internal Colossal.Mono.Cecil.CustomAttributeValueProjection projection`  

```csharp
internal Colossal.Mono.Cecil.CustomAttributeValueProjection projection;
```

- `internal readonly System.UInt32 signature`  

```csharp
internal readonly System.UInt32 signature;
```

- `internal System.Boolean resolved`  

```csharp
internal System.Boolean resolved;
```

- `private Colossal.Mono.Cecil.MethodReference constructor`  

```csharp
private Colossal.Mono.Cecil.MethodReference constructor;
```

- `private System.Byte[] blob`  

```csharp
private System.Byte[] blob;
```

- `internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeArgument> arguments`  

```csharp
internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeArgument> arguments;
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

- `public Colossal.Mono.Cecil.MethodReference Constructor { get; set }`  

```csharp
public Colossal.Mono.Cecil.MethodReference Constructor { get; set; }
```

- `public Colossal.Mono.Cecil.TypeReference AttributeType { get }`  

```csharp
public Colossal.Mono.Cecil.TypeReference AttributeType { get; }
```

- `public System.Boolean IsResolved { get }`  

```csharp
public System.Boolean IsResolved { get; }
```

- `public System.Boolean HasConstructorArguments { get }`  

```csharp
public System.Boolean HasConstructorArguments { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeArgument> ConstructorArguments { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeArgument> ConstructorArguments { get; }
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

- `internal System.Boolean HasImage { internal get }`  

```csharp
internal System.Boolean HasImage { internal get; }
```

- `internal Colossal.Mono.Cecil.ModuleDefinition Module { internal get }`  

```csharp
internal Colossal.Mono.Cecil.ModuleDefinition Module { internal get; }
```


## Constructors

- `internal CustomAttribute(System.UInt32 signature, Colossal.Mono.Cecil.MethodReference constructor)`  

```csharp
internal CustomAttribute(System.UInt32 signature, Colossal.Mono.Cecil.MethodReference constructor);
```

- `public CustomAttribute(Colossal.Mono.Cecil.MethodReference constructor)`  

```csharp
public CustomAttribute(Colossal.Mono.Cecil.MethodReference constructor);
```

- `public CustomAttribute(Colossal.Mono.Cecil.MethodReference constructor, System.Byte[] blob)`  

```csharp
public CustomAttribute(Colossal.Mono.Cecil.MethodReference constructor, System.Byte[] blob);
```


## Methods

- `private <Resolve>b__35_0(Colossal.Mono.Cecil.CustomAttribute attribute, Colossal.Mono.Cecil.MetadataReader reader) : System.Void`  

```csharp
private System.Void <Resolve>b__35_0(Colossal.Mono.Cecil.CustomAttribute attribute, Colossal.Mono.Cecil.MetadataReader reader);
```

- `public GetBlob() : System.Byte[]`  

```csharp
public System.Byte[] GetBlob();
```

- `private Resolve() : System.Void`  

```csharp
private System.Void Resolve();
```


## Nested types

- `Colossal.Mono.Cecil.CustomAttribute+<>c`  

