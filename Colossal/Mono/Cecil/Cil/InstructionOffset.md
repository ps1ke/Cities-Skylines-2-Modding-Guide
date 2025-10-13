# Colossal.Mono.Cecil.Cil.InstructionOffset

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct InstructionOffset
{
    private readonly Colossal.Mono.Cecil.Cil.Instruction instruction;
    private readonly System.Nullable<System.Int32> offset;

    public System.Int32 Offset { get; }
    public System.Boolean IsEndOfMethod { get; }
    internal System.Boolean IsResolved { internal get; }
    internal Colossal.Mono.Cecil.Cil.Instruction ResolvedInstruction { internal get; }

    public InstructionOffset(Colossal.Mono.Cecil.Cil.Instruction instruction);
    public InstructionOffset(System.Int32 offset);

}
```


## Fields

- `private readonly Colossal.Mono.Cecil.Cil.Instruction instruction`  

```csharp
private readonly Colossal.Mono.Cecil.Cil.Instruction instruction;
```

- `private readonly System.Nullable<System.Int32> offset`  

```csharp
private readonly System.Nullable<System.Int32> offset;
```


## Properties

- `public System.Int32 Offset { get }`  

```csharp
public System.Int32 Offset { get; }
```

- `public System.Boolean IsEndOfMethod { get }`  

```csharp
public System.Boolean IsEndOfMethod { get; }
```

- `internal System.Boolean IsResolved { internal get }`  

```csharp
internal System.Boolean IsResolved { internal get; }
```

- `internal Colossal.Mono.Cecil.Cil.Instruction ResolvedInstruction { internal get }`  

```csharp
internal Colossal.Mono.Cecil.Cil.Instruction ResolvedInstruction { internal get; }
```


## Constructors

- `public InstructionOffset(Colossal.Mono.Cecil.Cil.Instruction instruction)`  

```csharp
public InstructionOffset(Colossal.Mono.Cecil.Cil.Instruction instruction);
```

- `public InstructionOffset(System.Int32 offset)`  

```csharp
public InstructionOffset(System.Int32 offset);
```


