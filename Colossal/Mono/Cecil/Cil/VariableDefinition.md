# Colossal.Mono.Cecil.Cil.VariableDefinition

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.Cil.VariableReference`  

## Code

```csharp
public sealed class VariableDefinition : Colossal.Mono.Cecil.Cil.VariableReference
{
    public System.Boolean IsPinned { get; }

    public VariableDefinition(Colossal.Mono.Cecil.TypeReference variableType);

    public virtual Colossal.Mono.Cecil.Cil.VariableDefinition Resolve();
}
```


## Properties

- `public System.Boolean IsPinned { get }`  

```csharp
public System.Boolean IsPinned { get; }
```


## Constructors

- `public VariableDefinition(Colossal.Mono.Cecil.TypeReference variableType)`  

```csharp
public VariableDefinition(Colossal.Mono.Cecil.TypeReference variableType);
```


## Methods

- `public virtual Resolve() : Colossal.Mono.Cecil.Cil.VariableDefinition`  

```csharp
public virtual Colossal.Mono.Cecil.Cil.VariableDefinition Resolve();
```


