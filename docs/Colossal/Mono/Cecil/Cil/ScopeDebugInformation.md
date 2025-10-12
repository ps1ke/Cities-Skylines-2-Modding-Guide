# Colossal.Mono.Cecil.Cil.ScopeDebugInformation

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.Cil.DebugInformation`  
**Implements:** `Colossal.Mono.Cecil.Cil.ICustomDebugInformationProvider`, `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Fields

- `internal Colossal.Mono.Cecil.Cil.InstructionOffset start`  
- `internal Colossal.Mono.Cecil.Cil.InstructionOffset end`  
- `internal Colossal.Mono.Cecil.Cil.ImportDebugInformation import`  
- `internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.ScopeDebugInformation> scopes`  
- `internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.VariableDebugInformation> variables`  
- `internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.ConstantDebugInformation> constants`  

## Properties

- `public Colossal.Mono.Cecil.Cil.InstructionOffset Start { get; set }`  
- `public Colossal.Mono.Cecil.Cil.InstructionOffset End { get; set }`  
- `public Colossal.Mono.Cecil.Cil.ImportDebugInformation Import { get; set }`  
- `public System.Boolean HasScopes { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.ScopeDebugInformation> Scopes { get }`  
- `public System.Boolean HasVariables { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.VariableDebugInformation> Variables { get }`  
- `public System.Boolean HasConstants { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.ConstantDebugInformation> Constants { get }`  

## Constructors

- `internal ScopeDebugInformation()`  
- `public ScopeDebugInformation(Colossal.Mono.Cecil.Cil.Instruction start, Colossal.Mono.Cecil.Cil.Instruction end)`  

## Methods

- `public TryGetName(Colossal.Mono.Cecil.Cil.VariableDefinition variable, System.String& name) : System.Boolean`  

