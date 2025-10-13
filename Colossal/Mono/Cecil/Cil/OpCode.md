# Colossal.Mono.Cecil.Cil.OpCode

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Colossal.Mono.Cecil.Cil.OpCode>`  

## Code

```csharp
public sealed struct OpCode : System.IEquatable<Colossal.Mono.Cecil.Cil.OpCode>
{
    private readonly System.Byte op1;
    private readonly System.Byte op2;
    private readonly System.Byte code;
    private readonly System.Byte flow_control;
    private readonly System.Byte opcode_type;
    private readonly System.Byte operand_type;
    private readonly System.Byte stack_behavior_pop;
    private readonly System.Byte stack_behavior_push;

    public System.String Name { get; }
    public System.Int32 Size { get; }
    public System.Byte Op1 { get; }
    public System.Byte Op2 { get; }
    public System.Int16 Value { get; }
    public Colossal.Mono.Cecil.Cil.Code Code { get; }
    public Colossal.Mono.Cecil.Cil.FlowControl FlowControl { get; }
    public Colossal.Mono.Cecil.Cil.OpCodeType OpCodeType { get; }
    public Colossal.Mono.Cecil.Cil.OperandType OperandType { get; }
    public Colossal.Mono.Cecil.Cil.StackBehaviour StackBehaviourPop { get; }
    public Colossal.Mono.Cecil.Cil.StackBehaviour StackBehaviourPush { get; }

    internal OpCode(System.Int32 x, System.Int32 y);

    public virtual System.Boolean Equals(System.Object obj);
    public System.Boolean Equals(Colossal.Mono.Cecil.Cil.OpCode opcode);
    public virtual System.Int32 GetHashCode();
    public virtual System.String ToString();
}
```


## Fields

- `private readonly System.Byte op1`  

```csharp
private readonly System.Byte op1;
```

- `private readonly System.Byte op2`  

```csharp
private readonly System.Byte op2;
```

- `private readonly System.Byte code`  

```csharp
private readonly System.Byte code;
```

- `private readonly System.Byte flow_control`  

```csharp
private readonly System.Byte flow_control;
```

- `private readonly System.Byte opcode_type`  

```csharp
private readonly System.Byte opcode_type;
```

- `private readonly System.Byte operand_type`  

```csharp
private readonly System.Byte operand_type;
```

- `private readonly System.Byte stack_behavior_pop`  

```csharp
private readonly System.Byte stack_behavior_pop;
```

- `private readonly System.Byte stack_behavior_push`  

```csharp
private readonly System.Byte stack_behavior_push;
```


## Properties

- `public System.String Name { get }`  

```csharp
public System.String Name { get; }
```

- `public System.Int32 Size { get }`  

```csharp
public System.Int32 Size { get; }
```

- `public System.Byte Op1 { get }`  

```csharp
public System.Byte Op1 { get; }
```

- `public System.Byte Op2 { get }`  

```csharp
public System.Byte Op2 { get; }
```

- `public System.Int16 Value { get }`  

```csharp
public System.Int16 Value { get; }
```

- `public Colossal.Mono.Cecil.Cil.Code Code { get }`  

```csharp
public Colossal.Mono.Cecil.Cil.Code Code { get; }
```

- `public Colossal.Mono.Cecil.Cil.FlowControl FlowControl { get }`  

```csharp
public Colossal.Mono.Cecil.Cil.FlowControl FlowControl { get; }
```

- `public Colossal.Mono.Cecil.Cil.OpCodeType OpCodeType { get }`  

```csharp
public Colossal.Mono.Cecil.Cil.OpCodeType OpCodeType { get; }
```

- `public Colossal.Mono.Cecil.Cil.OperandType OperandType { get }`  

```csharp
public Colossal.Mono.Cecil.Cil.OperandType OperandType { get; }
```

- `public Colossal.Mono.Cecil.Cil.StackBehaviour StackBehaviourPop { get }`  

```csharp
public Colossal.Mono.Cecil.Cil.StackBehaviour StackBehaviourPop { get; }
```

- `public Colossal.Mono.Cecil.Cil.StackBehaviour StackBehaviourPush { get }`  

```csharp
public Colossal.Mono.Cecil.Cil.StackBehaviour StackBehaviourPush { get; }
```


## Constructors

- `internal OpCode(System.Int32 x, System.Int32 y)`  

```csharp
internal OpCode(System.Int32 x, System.Int32 y);
```


## Methods

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public Equals(Colossal.Mono.Cecil.Cil.OpCode opcode) : System.Boolean`  

```csharp
public System.Boolean Equals(Colossal.Mono.Cecil.Cil.OpCode opcode);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


