# Colossal.Mono.Cecil.EventDefinition

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.EventReference`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`, `Colossal.Mono.Cecil.IMemberDefinition`, `Colossal.Mono.Cecil.ICustomAttributeProvider`  

## Code

```csharp
public sealed class EventDefinition : Colossal.Mono.Cecil.EventReference, Colossal.Mono.Cecil.IMetadataTokenProvider, Colossal.Mono.Cecil.IMemberDefinition, Colossal.Mono.Cecil.ICustomAttributeProvider
{
    private System.UInt16 attributes;
    private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> custom_attributes;
    internal Colossal.Mono.Cecil.MethodDefinition add_method;
    internal Colossal.Mono.Cecil.MethodDefinition invoke_method;
    internal Colossal.Mono.Cecil.MethodDefinition remove_method;
    internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodDefinition> other_methods;

    public Colossal.Mono.Cecil.EventAttributes Attributes { get; set; }
    public Colossal.Mono.Cecil.MethodDefinition AddMethod { get; set; }
    public Colossal.Mono.Cecil.MethodDefinition InvokeMethod { get; set; }
    public Colossal.Mono.Cecil.MethodDefinition RemoveMethod { get; set; }
    public System.Boolean HasOtherMethods { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodDefinition> OtherMethods { get; }
    public System.Boolean HasCustomAttributes { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get; }
    public System.Boolean IsSpecialName { get; set; }
    public System.Boolean IsRuntimeSpecialName { get; set; }
    public Colossal.Mono.Cecil.TypeDefinition DeclaringType { get; set; }
    public System.Boolean IsDefinition { get; }

    public EventDefinition(System.String name, Colossal.Mono.Cecil.EventAttributes attributes, Colossal.Mono.Cecil.TypeReference eventType);

    private System.Void InitializeMethods();
    public virtual Colossal.Mono.Cecil.EventDefinition Resolve();
}
```


## Fields

- `private System.UInt16 attributes`  

```csharp
private System.UInt16 attributes;
```

- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> custom_attributes`  

```csharp
private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> custom_attributes;
```

- `internal Colossal.Mono.Cecil.MethodDefinition add_method`  

```csharp
internal Colossal.Mono.Cecil.MethodDefinition add_method;
```

- `internal Colossal.Mono.Cecil.MethodDefinition invoke_method`  

```csharp
internal Colossal.Mono.Cecil.MethodDefinition invoke_method;
```

- `internal Colossal.Mono.Cecil.MethodDefinition remove_method`  

```csharp
internal Colossal.Mono.Cecil.MethodDefinition remove_method;
```

- `internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodDefinition> other_methods`  

```csharp
internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodDefinition> other_methods;
```


## Properties

- `public Colossal.Mono.Cecil.EventAttributes Attributes { get; set }`  

```csharp
public Colossal.Mono.Cecil.EventAttributes Attributes { get; set; }
```

- `public Colossal.Mono.Cecil.MethodDefinition AddMethod { get; set }`  

```csharp
public Colossal.Mono.Cecil.MethodDefinition AddMethod { get; set; }
```

- `public Colossal.Mono.Cecil.MethodDefinition InvokeMethod { get; set }`  

```csharp
public Colossal.Mono.Cecil.MethodDefinition InvokeMethod { get; set; }
```

- `public Colossal.Mono.Cecil.MethodDefinition RemoveMethod { get; set }`  

```csharp
public Colossal.Mono.Cecil.MethodDefinition RemoveMethod { get; set; }
```

- `public System.Boolean HasOtherMethods { get }`  

```csharp
public System.Boolean HasOtherMethods { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodDefinition> OtherMethods { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodDefinition> OtherMethods { get; }
```

- `public System.Boolean HasCustomAttributes { get }`  

```csharp
public System.Boolean HasCustomAttributes { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get; }
```

- `public System.Boolean IsSpecialName { get; set }`  

```csharp
public System.Boolean IsSpecialName { get; set; }
```

- `public System.Boolean IsRuntimeSpecialName { get; set }`  

```csharp
public System.Boolean IsRuntimeSpecialName { get; set; }
```

- `public Colossal.Mono.Cecil.TypeDefinition DeclaringType { get; set }`  

```csharp
public Colossal.Mono.Cecil.TypeDefinition DeclaringType { get; set; }
```

- `public System.Boolean IsDefinition { get }`  

```csharp
public System.Boolean IsDefinition { get; }
```


## Constructors

- `public EventDefinition(System.String name, Colossal.Mono.Cecil.EventAttributes attributes, Colossal.Mono.Cecil.TypeReference eventType)`  

```csharp
public EventDefinition(System.String name, Colossal.Mono.Cecil.EventAttributes attributes, Colossal.Mono.Cecil.TypeReference eventType);
```


## Methods

- `private InitializeMethods() : System.Void`  

```csharp
private System.Void InitializeMethods();
```

- `public virtual Resolve() : Colossal.Mono.Cecil.EventDefinition`  

```csharp
public virtual Colossal.Mono.Cecil.EventDefinition Resolve();
```


## Nested types

- `Colossal.Mono.Cecil.EventDefinition+<>c`  

