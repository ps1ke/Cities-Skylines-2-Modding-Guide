# Colossal.Mono.Cecil.Cil.Instruction

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `System.Object`  

## Code

```csharp
public sealed class Instruction
{
    internal System.Int32 offset;
    internal Colossal.Mono.Cecil.Cil.OpCode opcode;
    internal System.Object operand;
    internal Colossal.Mono.Cecil.Cil.Instruction previous;
    internal Colossal.Mono.Cecil.Cil.Instruction next;

    public System.Int32 Offset { get; set; }
    public Colossal.Mono.Cecil.Cil.OpCode OpCode { get; set; }
    public System.Object Operand { get; set; }
    public Colossal.Mono.Cecil.Cil.Instruction Previous { get; set; }
    public Colossal.Mono.Cecil.Cil.Instruction Next { get; set; }

    internal Instruction(System.Int32 offset, Colossal.Mono.Cecil.Cil.OpCode opCode);
    internal Instruction(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Object operand);

    private static System.Void AppendLabel(System.Text.StringBuilder builder, Colossal.Mono.Cecil.Cil.Instruction instruction);
    public static Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode);
    public static Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.TypeReference type);
    public static Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.CallSite site);
    public static Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.MethodReference method);
    public static Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.FieldReference field);
    public static Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.String value);
    public static Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.SByte value);
    public static Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Byte value);
    public static Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int32 value);
    public static Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int64 value);
    public static Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Single value);
    public static Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Double value);
    public static Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.Instruction target);
    public static Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.Instruction[] targets);
    public static Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.VariableDefinition variable);
    public static Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.ParameterDefinition parameter);
    public System.Int32 GetSize();
    public virtual System.String ToString();
}
```


## Fields

- `internal System.Int32 offset`  

```csharp
internal System.Int32 offset;
```

- `internal Colossal.Mono.Cecil.Cil.OpCode opcode`  

```csharp
internal Colossal.Mono.Cecil.Cil.OpCode opcode;
```

- `internal System.Object operand`  

```csharp
internal System.Object operand;
```

- `internal Colossal.Mono.Cecil.Cil.Instruction previous`  

```csharp
internal Colossal.Mono.Cecil.Cil.Instruction previous;
```

- `internal Colossal.Mono.Cecil.Cil.Instruction next`  

```csharp
internal Colossal.Mono.Cecil.Cil.Instruction next;
```


## Properties

- `public System.Int32 Offset { get; set }`  

```csharp
public System.Int32 Offset { get; set; }
```

- `public Colossal.Mono.Cecil.Cil.OpCode OpCode { get; set }`  

```csharp
public Colossal.Mono.Cecil.Cil.OpCode OpCode { get; set; }
```

- `public System.Object Operand { get; set }`  

```csharp
public System.Object Operand { get; set; }
```

- `public Colossal.Mono.Cecil.Cil.Instruction Previous { get; set }`  

```csharp
public Colossal.Mono.Cecil.Cil.Instruction Previous { get; set; }
```

- `public Colossal.Mono.Cecil.Cil.Instruction Next { get; set }`  

```csharp
public Colossal.Mono.Cecil.Cil.Instruction Next { get; set; }
```


## Constructors

- `internal Instruction(System.Int32 offset, Colossal.Mono.Cecil.Cil.OpCode opCode)`  

```csharp
internal Instruction(System.Int32 offset, Colossal.Mono.Cecil.Cil.OpCode opCode);
```

- `internal Instruction(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Object operand)`  

```csharp
internal Instruction(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Object operand);
```


## Methods

- `private static AppendLabel(System.Text.StringBuilder builder, Colossal.Mono.Cecil.Cil.Instruction instruction) : System.Void`  

```csharp
private static System.Void AppendLabel(System.Text.StringBuilder builder, Colossal.Mono.Cecil.Cil.Instruction instruction);
```

- `public static Create(Colossal.Mono.Cecil.Cil.OpCode opcode) : Colossal.Mono.Cecil.Cil.Instruction`  

```csharp
public static Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode);
```

- `public static Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.TypeReference type) : Colossal.Mono.Cecil.Cil.Instruction`  

```csharp
public static Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.TypeReference type);
```

- `public static Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.CallSite site) : Colossal.Mono.Cecil.Cil.Instruction`  

```csharp
public static Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.CallSite site);
```

- `public static Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.MethodReference method) : Colossal.Mono.Cecil.Cil.Instruction`  

```csharp
public static Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.MethodReference method);
```

- `public static Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.FieldReference field) : Colossal.Mono.Cecil.Cil.Instruction`  

```csharp
public static Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.FieldReference field);
```

- `public static Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.String value) : Colossal.Mono.Cecil.Cil.Instruction`  

```csharp
public static Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.String value);
```

- `public static Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.SByte value) : Colossal.Mono.Cecil.Cil.Instruction`  

```csharp
public static Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.SByte value);
```

- `public static Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Byte value) : Colossal.Mono.Cecil.Cil.Instruction`  

```csharp
public static Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Byte value);
```

- `public static Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int32 value) : Colossal.Mono.Cecil.Cil.Instruction`  

```csharp
public static Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int32 value);
```

- `public static Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int64 value) : Colossal.Mono.Cecil.Cil.Instruction`  

```csharp
public static Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int64 value);
```

- `public static Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Single value) : Colossal.Mono.Cecil.Cil.Instruction`  

```csharp
public static Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Single value);
```

- `public static Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Double value) : Colossal.Mono.Cecil.Cil.Instruction`  

```csharp
public static Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Double value);
```

- `public static Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.Instruction target) : Colossal.Mono.Cecil.Cil.Instruction`  

```csharp
public static Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.Instruction target);
```

- `public static Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.Instruction[] targets) : Colossal.Mono.Cecil.Cil.Instruction`  

```csharp
public static Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.Instruction[] targets);
```

- `public static Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.VariableDefinition variable) : Colossal.Mono.Cecil.Cil.Instruction`  

```csharp
public static Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.VariableDefinition variable);
```

- `public static Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.ParameterDefinition parameter) : Colossal.Mono.Cecil.Cil.Instruction`  

```csharp
public static Colossal.Mono.Cecil.Cil.Instruction Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.ParameterDefinition parameter);
```

- `public GetSize() : System.Int32`  

```csharp
public System.Int32 GetSize();
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


