# Colossal.Mono.Cecil.Cil.SequencePoint

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `System.Object`  

## Fields

- `internal Colossal.Mono.Cecil.Cil.InstructionOffset offset`  
- `private Colossal.Mono.Cecil.Cil.Document document`  
- `private System.Int32 start_line`  
- `private System.Int32 start_column`  
- `private System.Int32 end_line`  
- `private System.Int32 end_column`  

## Properties

- `public System.Int32 Offset { get }`  
- `public System.Int32 StartLine { get; set }`  
- `public System.Int32 StartColumn { get; set }`  
- `public System.Int32 EndLine { get; set }`  
- `public System.Int32 EndColumn { get; set }`  
- `public System.Boolean IsHidden { get }`  
- `public Colossal.Mono.Cecil.Cil.Document Document { get; set }`  

## Constructors

- `internal SequencePoint(System.Int32 offset, Colossal.Mono.Cecil.Cil.Document document)`  
- `public SequencePoint(Colossal.Mono.Cecil.Cil.Instruction instruction, Colossal.Mono.Cecil.Cil.Document document)`  

