# Colossal.Mono.Cecil.Mdb.MdbWriter

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Mdb`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.Cil.ISymbolWriter`, `System.IDisposable`  

## Fields

- `private readonly Colossal.Mono.Cecil.ModuleDefinition module`  
- `private readonly Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolWriter writer`  
- `private readonly System.Collections.Generic.Dictionary<System.String, Colossal.Mono.Cecil.Mdb.MdbWriter+SourceFile> source_files`  

## Constructors

- `public MdbWriter(Colossal.Mono.Cecil.ModuleDefinition module, System.String assembly)`  

## Methods

- `public Dispose() : System.Void`  
- `public GetDebugHeader() : Colossal.Mono.Cecil.Cil.ImageDebugHeader`  
- `public GetReaderProvider() : Colossal.Mono.Cecil.Cil.ISymbolReaderProvider`  
- `private GetSourceFile(Colossal.Mono.Cecil.Cil.Document document) : Colossal.Mono.Cecil.Mdb.MdbWriter+SourceFile`  
- `private Populate(Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.SequencePoint> sequencePoints, System.Int32[] offsets, System.Int32[] startRows, System.Int32[] endRows, System.Int32[] startCols, System.Int32[] endCols, Colossal.Mono.Cecil.Mdb.MdbWriter+SourceFile& file) : System.Void`  
- `public Write(Colossal.Mono.Cecil.Cil.MethodDebugInformation info) : System.Void`  
- `private WriteRootScope(Colossal.Mono.Cecil.Cil.ScopeDebugInformation scope, Colossal.Mono.Cecil.Cil.MethodDebugInformation info) : System.Void`  
- `private WriteScope(Colossal.Mono.Cecil.Cil.ScopeDebugInformation scope, Colossal.Mono.Cecil.Cil.MethodDebugInformation info) : System.Void`  
- `private WriteScopes(Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.ScopeDebugInformation> scopes, Colossal.Mono.Cecil.Cil.MethodDebugInformation info) : System.Void`  
- `private WriteScopeVariables(Colossal.Mono.Cecil.Cil.ScopeDebugInformation scope) : System.Void`  

## Nested types

- `Colossal.Mono.Cecil.Mdb.MdbWriter+SourceFile`  
- `Colossal.Mono.Cecil.Mdb.MdbWriter+SourceMethod`  

