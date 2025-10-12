# Colossal.Mono.Cecil.Cil.OpCode

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Colossal.Mono.Cecil.Cil.OpCode>`  

## Fields

- `private readonly System.Byte op1`  
- `private readonly System.Byte op2`  
- `private readonly System.Byte code`  
- `private readonly System.Byte flow_control`  
- `private readonly System.Byte opcode_type`  
- `private readonly System.Byte operand_type`  
- `private readonly System.Byte stack_behavior_pop`  
- `private readonly System.Byte stack_behavior_push`  

## Properties

- `public System.String Name { get }`  
- `public System.Int32 Size { get }`  
- `public System.Byte Op1 { get }`  
- `public System.Byte Op2 { get }`  
- `public System.Int16 Value { get }`  
- `public Colossal.Mono.Cecil.Cil.Code Code { get }`  
- `public Colossal.Mono.Cecil.Cil.FlowControl FlowControl { get }`  
- `public Colossal.Mono.Cecil.Cil.OpCodeType OpCodeType { get }`  
- `public Colossal.Mono.Cecil.Cil.OperandType OperandType { get }`  
- `public Colossal.Mono.Cecil.Cil.StackBehaviour StackBehaviourPop { get }`  
- `public Colossal.Mono.Cecil.Cil.StackBehaviour StackBehaviourPush { get }`  

## Constructors

- `internal OpCode(System.Int32 x, System.Int32 y)`  

## Methods

- `public virtual Equals(System.Object obj) : System.Boolean`  
- `public Equals(Colossal.Mono.Cecil.Cil.OpCode opcode) : System.Boolean`  
- `public virtual GetHashCode() : System.Int32`  
- `public virtual ToString() : System.String`  

