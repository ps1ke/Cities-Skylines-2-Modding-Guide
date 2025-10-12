# Colossal.Mono.Cecil.Cil.Instruction

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `System.Object`  

## Fields

- `internal System.Int32 offset`  
- `internal Colossal.Mono.Cecil.Cil.OpCode opcode`  
- `internal System.Object operand`  
- `internal Colossal.Mono.Cecil.Cil.Instruction previous`  
- `internal Colossal.Mono.Cecil.Cil.Instruction next`  

## Properties

- `public System.Int32 Offset { get; set }`  
- `public Colossal.Mono.Cecil.Cil.OpCode OpCode { get; set }`  
- `public System.Object Operand { get; set }`  
- `public Colossal.Mono.Cecil.Cil.Instruction Previous { get; set }`  
- `public Colossal.Mono.Cecil.Cil.Instruction Next { get; set }`  

## Constructors

- `internal Instruction(System.Int32 offset, Colossal.Mono.Cecil.Cil.OpCode opCode)`  
- `internal Instruction(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Object operand)`  

## Methods

- `private static AppendLabel(System.Text.StringBuilder builder, Colossal.Mono.Cecil.Cil.Instruction instruction) : System.Void`  
- `public static Create(Colossal.Mono.Cecil.Cil.OpCode opcode) : Colossal.Mono.Cecil.Cil.Instruction`  
- `public static Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.TypeReference type) : Colossal.Mono.Cecil.Cil.Instruction`  
- `public static Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.CallSite site) : Colossal.Mono.Cecil.Cil.Instruction`  
- `public static Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.MethodReference method) : Colossal.Mono.Cecil.Cil.Instruction`  
- `public static Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.FieldReference field) : Colossal.Mono.Cecil.Cil.Instruction`  
- `public static Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.String value) : Colossal.Mono.Cecil.Cil.Instruction`  
- `public static Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.SByte value) : Colossal.Mono.Cecil.Cil.Instruction`  
- `public static Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Byte value) : Colossal.Mono.Cecil.Cil.Instruction`  
- `public static Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int32 value) : Colossal.Mono.Cecil.Cil.Instruction`  
- `public static Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int64 value) : Colossal.Mono.Cecil.Cil.Instruction`  
- `public static Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Single value) : Colossal.Mono.Cecil.Cil.Instruction`  
- `public static Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Double value) : Colossal.Mono.Cecil.Cil.Instruction`  
- `public static Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.Instruction target) : Colossal.Mono.Cecil.Cil.Instruction`  
- `public static Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.Instruction[] targets) : Colossal.Mono.Cecil.Cil.Instruction`  
- `public static Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.VariableDefinition variable) : Colossal.Mono.Cecil.Cil.Instruction`  
- `public static Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.ParameterDefinition parameter) : Colossal.Mono.Cecil.Cil.Instruction`  
- `public GetSize() : System.Int32`  
- `public virtual ToString() : System.String`  

