# Colossal.Mono.Cecil.Mdb.MdbReader

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Mdb`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.Cil.ISymbolReader`, `System.IDisposable`  

## Fields

- `private readonly Colossal.Mono.Cecil.ModuleDefinition module`  
- `private readonly Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile symbol_file`  
- `private readonly System.Collections.Generic.Dictionary<System.String, Colossal.Mono.Cecil.Cil.Document> documents`  

## Constructors

- `public MdbReader(Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile symFile)`  

## Methods

- `private static AddScope(Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.ScopeDebugInformation> scopes, Colossal.Mono.Cecil.Cil.ScopeDebugInformation scope) : System.Boolean`  
- `public Dispose() : System.Void`  
- `private GetDocument(Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry file) : Colossal.Mono.Cecil.Cil.Document`  
- `public GetWriterProvider() : Colossal.Mono.Cecil.Cil.ISymbolWriterProvider`  
- `private LineToSequencePoint(Colossal.Mono.CompilerServices.SymbolWriter.LineNumberEntry line) : Colossal.Mono.Cecil.Cil.SequencePoint`  
- `public ProcessDebugHeader(Colossal.Mono.Cecil.Cil.ImageDebugHeader header) : System.Boolean`  
- `public Read(Colossal.Mono.Cecil.MethodDefinition method) : Colossal.Mono.Cecil.Cil.MethodDebugInformation`  
- `private static ReadCodeSize(Colossal.Mono.Cecil.MethodDefinition method) : System.Int32`  
- `private ReadLineNumbers(Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry entry, Colossal.Mono.Cecil.Cil.MethodDebugInformation info) : System.Void`  
- `private static ReadLocalVariables(Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry entry, Colossal.Mono.Cecil.Cil.ScopeDebugInformation[] scopes) : System.Void`  
- `private static ReadScopes(Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry entry, Colossal.Mono.Cecil.Cil.MethodDebugInformation info) : Colossal.Mono.Cecil.Cil.ScopeDebugInformation[]`  

## Nested types

- `Colossal.Mono.Cecil.Mdb.MdbReader+<>c`  

