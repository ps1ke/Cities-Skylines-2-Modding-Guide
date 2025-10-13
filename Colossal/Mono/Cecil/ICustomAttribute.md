# Colossal.Mono.Cecil.ICustomAttribute

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface ICustomAttribute
{
    public Colossal.Mono.Cecil.TypeReference AttributeType { get; }
    public System.Boolean HasFields { get; }
    public System.Boolean HasProperties { get; }
    public System.Boolean HasConstructorArguments { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeNamedArgument> Fields { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeNamedArgument> Properties { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeArgument> ConstructorArguments { get; }

}
```


## Properties

- `public Colossal.Mono.Cecil.TypeReference AttributeType { get }`  

```csharp
public Colossal.Mono.Cecil.TypeReference AttributeType { get; }
```

- `public System.Boolean HasFields { get }`  

```csharp
public System.Boolean HasFields { get; }
```

- `public System.Boolean HasProperties { get }`  

```csharp
public System.Boolean HasProperties { get; }
```

- `public System.Boolean HasConstructorArguments { get }`  

```csharp
public System.Boolean HasConstructorArguments { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeNamedArgument> Fields { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeNamedArgument> Fields { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeNamedArgument> Properties { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeNamedArgument> Properties { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeArgument> ConstructorArguments { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeArgument> ConstructorArguments { get; }
```


