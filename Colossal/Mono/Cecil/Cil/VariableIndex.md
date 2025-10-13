# Colossal.Mono.Cecil.Cil.VariableIndex

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct VariableIndex
{
    private readonly Colossal.Mono.Cecil.Cil.VariableDefinition variable;
    private readonly System.Nullable<System.Int32> index;

    public System.Int32 Index { get; }
    internal System.Boolean IsResolved { internal get; }
    internal Colossal.Mono.Cecil.Cil.VariableDefinition ResolvedVariable { internal get; }

    public VariableIndex(Colossal.Mono.Cecil.Cil.VariableDefinition variable);
    public VariableIndex(System.Int32 index);

}
```


## Fields

- `private readonly Colossal.Mono.Cecil.Cil.VariableDefinition variable`  

```csharp
private readonly Colossal.Mono.Cecil.Cil.VariableDefinition variable;
```

- `private readonly System.Nullable<System.Int32> index`  

```csharp
private readonly System.Nullable<System.Int32> index;
```


## Properties

- `public System.Int32 Index { get }`  

```csharp
public System.Int32 Index { get; }
```

- `internal System.Boolean IsResolved { internal get }`  

```csharp
internal System.Boolean IsResolved { internal get; }
```

- `internal Colossal.Mono.Cecil.Cil.VariableDefinition ResolvedVariable { internal get }`  

```csharp
internal Colossal.Mono.Cecil.Cil.VariableDefinition ResolvedVariable { internal get; }
```


## Constructors

- `public VariableIndex(Colossal.Mono.Cecil.Cil.VariableDefinition variable)`  

```csharp
public VariableIndex(Colossal.Mono.Cecil.Cil.VariableDefinition variable);
```

- `public VariableIndex(System.Int32 index)`  

```csharp
public VariableIndex(System.Int32 index);
```


