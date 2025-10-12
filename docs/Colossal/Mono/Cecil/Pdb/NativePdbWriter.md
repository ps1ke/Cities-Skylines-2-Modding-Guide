# Colossal.Mono.Cecil.Pdb.NativePdbWriter

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Pdb`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.Cil.ISymbolWriter`, `System.IDisposable`  

## Fields

- `private readonly Colossal.Mono.Cecil.ModuleDefinition module`  
- `private readonly Colossal.Mono.Cecil.MetadataBuilder metadata`  
- `private readonly Colossal.Mono.Cecil.Pdb.SymWriter writer`  
- `private readonly System.Collections.Generic.Dictionary<System.String, Colossal.Mono.Cecil.Pdb.SymDocumentWriter> documents`  
- `private readonly System.Collections.Generic.Dictionary<Colossal.Mono.Cecil.Cil.ImportDebugInformation, Colossal.Mono.Cecil.MetadataToken> import_info_to_parent`  

## Constructors

- `internal NativePdbWriter(Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.Cecil.Pdb.SymWriter writer)`  

## Methods

- `private DefineAsyncCustomMetadata(Colossal.Mono.Cecil.Cil.MethodDebugInformation info) : System.Void`  
- `private DefineConstant(Colossal.Mono.Cecil.Cil.ConstantDebugInformation constant) : System.Void`  
- `private DefineCustomMetadata(Colossal.Mono.Cecil.Cil.MethodDebugInformation info, Colossal.Mono.Cecil.MetadataToken import_parent) : System.Void`  
- `private DefineLocalVariable(Colossal.Mono.Cecil.Cil.VariableDebugInformation variable, System.Int32 local_var_token, System.Int32 start_offset, System.Int32 end_offset) : System.Void`  
- `private DefineScope(Colossal.Mono.Cecil.Cil.ScopeDebugInformation scope, Colossal.Mono.Cecil.Cil.MethodDebugInformation info, Colossal.Mono.Cecil.MetadataToken& import_parent) : System.Void`  
- `private DefineSequencePoints(Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.SequencePoint> sequence_points) : System.Void`  
- `public Dispose() : System.Void`  
- `public GetDebugHeader() : Colossal.Mono.Cecil.Cil.ImageDebugHeader`  
- `private GetDocument(Colossal.Mono.Cecil.Cil.Document document) : Colossal.Mono.Cecil.Pdb.SymDocumentWriter`  
- `public GetReaderProvider() : Colossal.Mono.Cecil.Cil.ISymbolReaderProvider`  
- `public Write(Colossal.Mono.Cecil.Cil.MethodDebugInformation info) : System.Void`  

## Nested types

- `Colossal.Mono.Cecil.Pdb.NativePdbWriter+<>c`  

