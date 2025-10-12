# Colossal.Mono.Cecil.Cil.MethodDebugInformation

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.Cil.DebugInformation`  
**Implements:** `Colossal.Mono.Cecil.Cil.ICustomDebugInformationProvider`, `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Fields

- `internal Colossal.Mono.Cecil.MethodDefinition method`  
- `internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.SequencePoint> sequence_points`  
- `internal Colossal.Mono.Cecil.Cil.ScopeDebugInformation scope`  
- `internal Colossal.Mono.Cecil.MethodDefinition kickoff_method`  
- `internal System.Int32 code_size`  
- `internal Colossal.Mono.Cecil.MetadataToken local_var_token`  

## Properties

- `public Colossal.Mono.Cecil.MethodDefinition Method { get }`  
- `public System.Boolean HasSequencePoints { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.SequencePoint> SequencePoints { get }`  
- `public Colossal.Mono.Cecil.Cil.ScopeDebugInformation Scope { get; set }`  
- `public Colossal.Mono.Cecil.MethodDefinition StateMachineKickOffMethod { get; set }`  

## Constructors

- `internal MethodDebugInformation(Colossal.Mono.Cecil.MethodDefinition method)`  

## Methods

- `public GetScopes() : System.Collections.Generic.IEnumerable<Colossal.Mono.Cecil.Cil.ScopeDebugInformation>`  
- `private static GetScopes(System.Collections.Generic.IList<Colossal.Mono.Cecil.Cil.ScopeDebugInformation> scopes) : System.Collections.Generic.IEnumerable<Colossal.Mono.Cecil.Cil.ScopeDebugInformation>`  
- `public GetSequencePoint(Colossal.Mono.Cecil.Cil.Instruction instruction) : Colossal.Mono.Cecil.Cil.SequencePoint`  
- `public GetSequencePointMapping() : System.Collections.Generic.IDictionary<Colossal.Mono.Cecil.Cil.Instruction, Colossal.Mono.Cecil.Cil.SequencePoint>`  
- `public TryGetName(Colossal.Mono.Cecil.Cil.VariableDefinition variable, System.String& name) : System.Boolean`  

## Nested types

- `Colossal.Mono.Cecil.Cil.MethodDebugInformation+<GetScopes>d__22`  

