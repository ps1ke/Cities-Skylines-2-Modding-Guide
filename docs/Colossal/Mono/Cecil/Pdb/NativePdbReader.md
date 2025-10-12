# Colossal.Mono.Cecil.Pdb.NativePdbReader

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Pdb`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.Cil.ISymbolReader`, `System.IDisposable`  

## Fields

- `private readonly Colossal.Mono.Disposable<System.IO.Stream> pdb_file`  
- `private readonly System.Collections.Generic.Dictionary<System.String, Colossal.Mono.Cecil.Cil.Document> documents`  
- `private readonly System.Collections.Generic.Dictionary<System.UInt32, Microsoft.Cci.Pdb.PdbFunction> functions`  
- `private readonly System.Collections.Generic.Dictionary<Microsoft.Cci.Pdb.PdbScope, Colossal.Mono.Cecil.Cil.ImportDebugInformation> imports`  

## Constructors

- `internal NativePdbReader(Colossal.Mono.Disposable<System.IO.Stream> file)`  

## Methods

- `private static AddScope(Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.ScopeDebugInformation> scopes, Colossal.Mono.Cecil.Cil.ScopeDebugInformation scope) : System.Boolean`  
- `public Dispose() : System.Void`  
- `private GetDocument(Microsoft.Cci.Pdb.PdbSource source) : Colossal.Mono.Cecil.Cil.Document`  
- `private GetImport(System.UInt32 token, Colossal.Mono.Cecil.ModuleDefinition module) : Colossal.Mono.Cecil.Cil.ImportDebugInformation`  
- `private static GetImport(Microsoft.Cci.Pdb.PdbScope scope, Colossal.Mono.Cecil.ModuleDefinition module) : Colossal.Mono.Cecil.Cil.ImportDebugInformation`  
- `public GetWriterProvider() : Colossal.Mono.Cecil.Cil.ISymbolWriterProvider`  
- `private static IsMatchingEntry(Microsoft.Cci.Pdb.PdbInfo info, Colossal.Mono.Cecil.Cil.ImageDebugHeaderEntry entry) : System.Boolean`  
- `public ProcessDebugHeader(Colossal.Mono.Cecil.Cil.ImageDebugHeader header) : System.Boolean`  
- `public Read(Colossal.Mono.Cecil.MethodDefinition method) : Colossal.Mono.Cecil.Cil.MethodDebugInformation`  
- `private static ReadInt32(System.Byte[] bytes, System.Int32 start) : System.Int32`  
- `private static ReadLine(Microsoft.Cci.Pdb.PdbLine line, Colossal.Mono.Cecil.Cil.Document document, Colossal.Mono.Cecil.Cil.MethodDebugInformation info) : System.Void`  
- `private ReadLines(Microsoft.Cci.Pdb.PdbLines lines, Colossal.Mono.Cecil.Cil.MethodDebugInformation info) : System.Void`  
- `private ReadScopeAndLocals(Microsoft.Cci.Pdb.PdbScope[] scopes, Colossal.Mono.Cecil.Cil.MethodDebugInformation info) : Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.ScopeDebugInformation>`  
- `private ReadScopeAndLocals(Microsoft.Cci.Pdb.PdbScope scope, Colossal.Mono.Cecil.Cil.MethodDebugInformation info) : Colossal.Mono.Cecil.Cil.ScopeDebugInformation`  
- `private ReadSequencePoints(Microsoft.Cci.Pdb.PdbFunction function, Colossal.Mono.Cecil.Cil.MethodDebugInformation info) : System.Void`  

## Nested types

- `Colossal.Mono.Cecil.Pdb.NativePdbReader+<>c`  

