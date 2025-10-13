# Colossal.Mono.Cecil.PropertyReference

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class abstract public  

**Base:** `Colossal.Mono.Cecil.MemberReference`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Code

```csharp
public abstract class PropertyReference : Colossal.Mono.Cecil.MemberReference, Colossal.Mono.Cecil.IMetadataTokenProvider
{
    private Colossal.Mono.Cecil.TypeReference property_type;

    public Colossal.Mono.Cecil.TypeReference PropertyType { get; set; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ParameterDefinition> Parameters { get; }

    internal PropertyReference(System.String name, Colossal.Mono.Cecil.TypeReference propertyType);

    public abstract Colossal.Mono.Cecil.PropertyDefinition Resolve();
    protected virtual Colossal.Mono.Cecil.IMemberDefinition ResolveDefinition();
}
```


## Fields

- `private Colossal.Mono.Cecil.TypeReference property_type`  

```csharp
private Colossal.Mono.Cecil.TypeReference property_type;
```


## Properties

- `public Colossal.Mono.Cecil.TypeReference PropertyType { get; set }`  

```csharp
public Colossal.Mono.Cecil.TypeReference PropertyType { get; set; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ParameterDefinition> Parameters { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ParameterDefinition> Parameters { get; }
```


## Constructors

- `internal PropertyReference(System.String name, Colossal.Mono.Cecil.TypeReference propertyType)`  

```csharp
internal PropertyReference(System.String name, Colossal.Mono.Cecil.TypeReference propertyType);
```


## Methods

- `public abstract Resolve() : Colossal.Mono.Cecil.PropertyDefinition`  

```csharp
public abstract Colossal.Mono.Cecil.PropertyDefinition Resolve();
```

- `protected virtual ResolveDefinition() : Colossal.Mono.Cecil.IMemberDefinition`  

```csharp
protected virtual Colossal.Mono.Cecil.IMemberDefinition ResolveDefinition();
```


