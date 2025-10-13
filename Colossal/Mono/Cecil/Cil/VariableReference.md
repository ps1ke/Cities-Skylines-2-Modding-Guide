# Colossal.Mono.Cecil.Cil.VariableReference

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class abstract public  

**Base:** `System.Object`  

## Code

```csharp
public abstract class VariableReference
{
    internal System.Int32 index;
    protected Colossal.Mono.Cecil.TypeReference variable_type;

    public Colossal.Mono.Cecil.TypeReference VariableType { get; set; }
    public System.Int32 Index { get; }

    internal VariableReference(Colossal.Mono.Cecil.TypeReference variable_type);

    public abstract Colossal.Mono.Cecil.Cil.VariableDefinition Resolve();
    public virtual System.String ToString();
}
```


## Fields

- `internal System.Int32 index`  

```csharp
internal System.Int32 index;
```

- `protected Colossal.Mono.Cecil.TypeReference variable_type`  

```csharp
protected Colossal.Mono.Cecil.TypeReference variable_type;
```


## Properties

- `public Colossal.Mono.Cecil.TypeReference VariableType { get; set }`  

```csharp
public Colossal.Mono.Cecil.TypeReference VariableType { get; set; }
```

- `public System.Int32 Index { get }`  

```csharp
public System.Int32 Index { get; }
```


## Constructors

- `internal VariableReference(Colossal.Mono.Cecil.TypeReference variable_type)`  

```csharp
internal VariableReference(Colossal.Mono.Cecil.TypeReference variable_type);
```


## Methods

- `public abstract Resolve() : Colossal.Mono.Cecil.Cil.VariableDefinition`  

```csharp
public abstract Colossal.Mono.Cecil.Cil.VariableDefinition Resolve();
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


