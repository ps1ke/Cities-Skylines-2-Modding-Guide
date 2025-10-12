# Colossal.Mono.Cecil.Cil.ILProcessor

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `System.Object`  

## Fields

- `private readonly Colossal.Mono.Cecil.Cil.MethodBody body`  
- `private readonly Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.Instruction> instructions`  

## Properties

- `public Colossal.Mono.Cecil.Cil.MethodBody Body { get }`  

## Constructors

- `internal ILProcessor(Colossal.Mono.Cecil.Cil.MethodBody body)`  

## Methods

- `public Append(Colossal.Mono.Cecil.Cil.Instruction instruction) : System.Void`  
- `public Clear() : System.Void`  
- `public Create(Colossal.Mono.Cecil.Cil.OpCode opcode) : Colossal.Mono.Cecil.Cil.Instruction`  
- `public Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.TypeReference type) : Colossal.Mono.Cecil.Cil.Instruction`  
- `public Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.CallSite site) : Colossal.Mono.Cecil.Cil.Instruction`  
- `public Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.MethodReference method) : Colossal.Mono.Cecil.Cil.Instruction`  
- `public Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.FieldReference field) : Colossal.Mono.Cecil.Cil.Instruction`  
- `public Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.String value) : Colossal.Mono.Cecil.Cil.Instruction`  
- `public Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.SByte value) : Colossal.Mono.Cecil.Cil.Instruction`  
- `public Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Byte value) : Colossal.Mono.Cecil.Cil.Instruction`  
- `public Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int32 value) : Colossal.Mono.Cecil.Cil.Instruction`  
- `public Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int64 value) : Colossal.Mono.Cecil.Cil.Instruction`  
- `public Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Single value) : Colossal.Mono.Cecil.Cil.Instruction`  
- `public Create(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Double value) : Colossal.Mono.Cecil.Cil.Instruction`  
- `public Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.Instruction target) : Colossal.Mono.Cecil.Cil.Instruction`  
- `public Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.Instruction[] targets) : Colossal.Mono.Cecil.Cil.Instruction`  
- `public Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.VariableDefinition variable) : Colossal.Mono.Cecil.Cil.Instruction`  
- `public Create(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.ParameterDefinition parameter) : Colossal.Mono.Cecil.Cil.Instruction`  
- `public Emit(Colossal.Mono.Cecil.Cil.OpCode opcode) : System.Void`  
- `public Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.TypeReference type) : System.Void`  
- `public Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.MethodReference method) : System.Void`  
- `public Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.CallSite site) : System.Void`  
- `public Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.FieldReference field) : System.Void`  
- `public Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, System.String value) : System.Void`  
- `public Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Byte value) : System.Void`  
- `public Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, System.SByte value) : System.Void`  
- `public Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int32 value) : System.Void`  
- `public Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Int64 value) : System.Void`  
- `public Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Single value) : System.Void`  
- `public Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, System.Double value) : System.Void`  
- `public Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.Instruction target) : System.Void`  
- `public Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.Instruction[] targets) : System.Void`  
- `public Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.Cil.VariableDefinition variable) : System.Void`  
- `public Emit(Colossal.Mono.Cecil.Cil.OpCode opcode, Colossal.Mono.Cecil.ParameterDefinition parameter) : System.Void`  
- `public InsertAfter(Colossal.Mono.Cecil.Cil.Instruction target, Colossal.Mono.Cecil.Cil.Instruction instruction) : System.Void`  
- `public InsertAfter(System.Int32 index, Colossal.Mono.Cecil.Cil.Instruction instruction) : System.Void`  
- `public InsertBefore(Colossal.Mono.Cecil.Cil.Instruction target, Colossal.Mono.Cecil.Cil.Instruction instruction) : System.Void`  
- `public Remove(Colossal.Mono.Cecil.Cil.Instruction instruction) : System.Void`  
- `public RemoveAt(System.Int32 index) : System.Void`  
- `public Replace(Colossal.Mono.Cecil.Cil.Instruction target, Colossal.Mono.Cecil.Cil.Instruction instruction) : System.Void`  
- `public Replace(System.Int32 index, Colossal.Mono.Cecil.Cil.Instruction instruction) : System.Void`  

