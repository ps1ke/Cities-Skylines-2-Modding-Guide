# Colossal.Mono.Cecil.Cil.ILProcessor

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `System.Object`  

## Code

```csharp
public sealed class ILProcessor
{
    private readonly Colossal.Mono.Cecil.Cil.MethodBody body;
    private readonly Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.Instruction> instructions;

    public Colossal.Mono.Cecil.Cil.MethodBody Body { get; }

    internal ILProcessor(Colossal.Mono.Cecil.Cil.MethodBody body);

    public System.Void Append(Colossal.Mono.Cecil.Cil.Instruction instruction);
    public System.Void Clear();
    public Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode);
    public Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.TypeReference type);
    public Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.CallSite site);
    public Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.MethodReference method);
    public Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.FieldReference field);
    public Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.String value);
    public Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.SByte value);
    public Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Byte value);
    public Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int32 value);
    public Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int64 value);
    public Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Single value);
    public Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Double value);
    public Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.Instruction target);
    public Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.Instruction[] targets);
    public Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.VariableDefinition variable);
    public Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.ParameterDefinition parameter);
    public System.Void Emit(Colossal.Mono.Cecil.Cil.OpCode opcode);
    public System.Void Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.TypeReference type);
    public System.Void Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.MethodReference method);
    public System.Void Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.CallSite site);
    public System.Void Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.FieldReference field);
    public System.Void Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, System.String value);
    public System.Void Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Byte value);
    public System.Void Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, System.SByte value);
    public System.Void Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int32 value);
    public System.Void Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int64 value);
    public System.Void Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Single value);
    public System.Void Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Double value);
    public System.Void Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.Instruction target);
    public System.Void Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.Instruction[] targets);
    public System.Void Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.VariableDefinition variable);
    public System.Void Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.ParameterDefinition parameter);
    public System.Void InsertAfter(Colossal.Mono.Cecil.Cil.Instruction target, Colossal.Mono.Cecil.Cil.Instruction instruction);
    public System.Void InsertAfter(System.Int32 index, Colossal.Mono.Cecil.Cil.Instruction instruction);
    public System.Void InsertBefore(Colossal.Mono.Cecil.Cil.Instruction target, Colossal.Mono.Cecil.Cil.Instruction instruction);
    public System.Void Remove(Colossal.Mono.Cecil.Cil.Instruction instruction);
    public System.Void RemoveAt(System.Int32 index);
    public System.Void Replace(Colossal.Mono.Cecil.Cil.Instruction target, Colossal.Mono.Cecil.Cil.Instruction instruction);
    public System.Void Replace(System.Int32 index, Colossal.Mono.Cecil.Cil.Instruction instruction);
}
```


## Fields

- `private readonly Colossal.Mono.Cecil.Cil.MethodBody body`  

```csharp
private readonly Colossal.Mono.Cecil.Cil.MethodBody body;
```

- `private readonly Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.Instruction> instructions`  

```csharp
private readonly Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.Instruction> instructions;
```


## Properties

- `public Colossal.Mono.Cecil.Cil.MethodBody Body { get }`  

```csharp
public Colossal.Mono.Cecil.Cil.MethodBody Body { get; }
```


## Constructors

- `internal ILProcessor(Colossal.Mono.Cecil.Cil.MethodBody body)`  

```csharp
internal ILProcessor(Colossal.Mono.Cecil.Cil.MethodBody body);
```


## Methods

- `public Append(Colossal.Mono.Cecil.Cil.Instruction instruction) : System.Void`  

```csharp
public System.Void Append(Colossal.Mono.Cecil.Cil.Instruction instruction);
```

- `public Clear() : System.Void`  

```csharp
public System.Void Clear();
```

- `public Create(Colossal.Mono.Cecil.Cil.OpCode opcode) : Colossal.Mono.Cecil.Cil.Instruction`  

```csharp
public Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode);
```

- `public Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.TypeReference type) : Colossal.Mono.Cecil.Cil.Instruction`  

```csharp
public Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.TypeReference type);
```

- `public Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.CallSite site) : Colossal.Mono.Cecil.Cil.Instruction`  

```csharp
public Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.CallSite site);
```

- `public Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.MethodReference method) : Colossal.Mono.Cecil.Cil.Instruction`  

```csharp
public Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.MethodReference method);
```

- `public Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.FieldReference field) : Colossal.Mono.Cecil.Cil.Instruction`  

```csharp
public Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.FieldReference field);
```

- `public Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.String value) : Colossal.Mono.Cecil.Cil.Instruction`  

```csharp
public Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.String value);
```

- `public Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.SByte value) : Colossal.Mono.Cecil.Cil.Instruction`  

```csharp
public Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.SByte value);
```

- `public Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Byte value) : Colossal.Mono.Cecil.Cil.Instruction`  

```csharp
public Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Byte value);
```

- `public Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int32 value) : Colossal.Mono.Cecil.Cil.Instruction`  

```csharp
public Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int32 value);
```

- `public Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int64 value) : Colossal.Mono.Cecil.Cil.Instruction`  

```csharp
public Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int64 value);
```

- `public Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Single value) : Colossal.Mono.Cecil.Cil.Instruction`  

```csharp
public Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Single value);
```

- `public Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Double value) : Colossal.Mono.Cecil.Cil.Instruction`  

```csharp
public Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Double value);
```

- `public Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.Instruction target) : Colossal.Mono.Cecil.Cil.Instruction`  

```csharp
public Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.Instruction target);
```

- `public Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.Instruction[] targets) : Colossal.Mono.Cecil.Cil.Instruction`  

```csharp
public Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.Instruction[] targets);
```

- `public Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.VariableDefinition variable) : Colossal.Mono.Cecil.Cil.Instruction`  

```csharp
public Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.VariableDefinition variable);
```

- `public Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.ParameterDefinition parameter) : Colossal.Mono.Cecil.Cil.Instruction`  

```csharp
public Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.ParameterDefinition parameter);
```

- `public Emit(Colossal.Mono.Cecil.Cil.OpCode opcode) : System.Void`  

```csharp
public System.Void Emit(Colossal.Mono.Cecil.Cil.OpCode opcode);
```

- `public Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.TypeReference type) : System.Void`  

```csharp
public System.Void Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.TypeReference type);
```

- `public Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.MethodReference method) : System.Void`  

```csharp
public System.Void Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.MethodReference method);
```

- `public Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.CallSite site) : System.Void`  

```csharp
public System.Void Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.CallSite site);
```

- `public Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.FieldReference field) : System.Void`  

```csharp
public System.Void Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.FieldReference field);
```

- `public Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, System.String value) : System.Void`  

```csharp
public System.Void Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, System.String value);
```

- `public Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Byte value) : System.Void`  

```csharp
public System.Void Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Byte value);
```

- `public Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, System.SByte value) : System.Void`  

```csharp
public System.Void Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, System.SByte value);
```

- `public Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int32 value) : System.Void`  

```csharp
public System.Void Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int32 value);
```

- `public Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int64 value) : System.Void`  

```csharp
public System.Void Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int64 value);
```

- `public Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Single value) : System.Void`  

```csharp
public System.Void Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Single value);
```

- `public Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Double value) : System.Void`  

```csharp
public System.Void Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Double value);
```

- `public Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.Instruction target) : System.Void`  

```csharp
public System.Void Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.Instruction target);
```

- `public Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.Instruction[] targets) : System.Void`  

```csharp
public System.Void Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.Instruction[] targets);
```

- `public Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.VariableDefinition variable) : System.Void`  

```csharp
public System.Void Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.VariableDefinition variable);
```

- `public Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.ParameterDefinition parameter) : System.Void`  

```csharp
public System.Void Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.ParameterDefinition parameter);
```

- `public InsertAfter(Colossal.Mono.Cecil.Cil.Instruction target, Colossal.Mono.Cecil.Cil.Instruction instruction) : System.Void`  

```csharp
public System.Void InsertAfter(Colossal.Mono.Cecil.Cil.Instruction target, Colossal.Mono.Cecil.Cil.Instruction instruction);
```

- `public InsertAfter(System.Int32 index, Colossal.Mono.Cecil.Cil.Instruction instruction) : System.Void`  

```csharp
public System.Void InsertAfter(System.Int32 index, Colossal.Mono.Cecil.Cil.Instruction instruction);
```

- `public InsertBefore(Colossal.Mono.Cecil.Cil.Instruction target, Colossal.Mono.Cecil.Cil.Instruction instruction) : System.Void`  

```csharp
public System.Void InsertBefore(Colossal.Mono.Cecil.Cil.Instruction target, Colossal.Mono.Cecil.Cil.Instruction instruction);
```

- `public Remove(Colossal.Mono.Cecil.Cil.Instruction instruction) : System.Void`  

```csharp
public System.Void Remove(Colossal.Mono.Cecil.Cil.Instruction instruction);
```

- `public RemoveAt(System.Int32 index) : System.Void`  

```csharp
public System.Void RemoveAt(System.Int32 index);
```

- `public Replace(Colossal.Mono.Cecil.Cil.Instruction target, Colossal.Mono.Cecil.Cil.Instruction instruction) : System.Void`  

```csharp
public System.Void Replace(Colossal.Mono.Cecil.Cil.Instruction target, Colossal.Mono.Cecil.Cil.Instruction instruction);
```

- `public Replace(System.Int32 index, Colossal.Mono.Cecil.Cil.Instruction instruction) : System.Void`  

```csharp
public System.Void Replace(System.Int32 index, Colossal.Mono.Cecil.Cil.Instruction instruction);
```


