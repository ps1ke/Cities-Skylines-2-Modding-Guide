# Colossal.Mono.Cecil.Cil.AsyncMethodBodyDebugInformation

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.Cil.CustomDebugInformation`  
**Implements:** `Colossal.Mono.Cecil.Cil.ICustomDebugInformationProvider`, `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Fields

- `internal Colossal.Mono.Cecil.Cil.InstructionOffset catch_handler`  
- `internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.InstructionOffset> yields`  
- `internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.InstructionOffset> resumes`  
- `internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodDefinition> resume_methods`  
- `public static System.Guid KindIdentifier`  

## Properties

- `public Colossal.Mono.Cecil.Cil.InstructionOffset CatchHandler { get; set }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.InstructionOffset> Yields { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.InstructionOffset> Resumes { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodDefinition> ResumeMethods { get }`  
- `public Colossal.Mono.Cecil.Cil.CustomDebugInformationKind Kind { get }`  

## Constructors

- `internal AsyncMethodBodyDebugInformation(System.Int32 catchHandler)`  
- `public AsyncMethodBodyDebugInformation(Colossal.Mono.Cecil.Cil.Instruction catchHandler)`  
- `public AsyncMethodBodyDebugInformation()`  

