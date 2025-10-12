# Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolWriter

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.CompilerServices.SymbolWriter`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.SourceMethodBuilder> methods`  
- `private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry> sources`  
- `private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry> comp_units`  
- `protected readonly Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file`  
- `private System.String filename`  
- `private Colossal.Mono.CompilerServices.SymbolWriter.SourceMethodBuilder current_method`  
- `private System.Collections.Generic.Stack<Colossal.Mono.CompilerServices.SymbolWriter.SourceMethodBuilder> current_method_stack`  

## Properties

- `public Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile SymbolFile { get }`  

## Constructors

- `public MonoSymbolWriter(System.String filename)`  

## Methods

- `public CloseCompilerGeneratedBlock(System.Int32 end_offset) : System.Void`  
- `public CloseMethod() : System.Void`  
- `public CloseNamespace() : System.Void`  
- `public CloseScope(System.Int32 end_offset) : System.Void`  
- `public DefineAnonymousScope(System.Int32 id) : System.Void`  
- `public DefineCapturedLocal(System.Int32 scope_id, System.String name, System.String captured_name) : System.Void`  
- `public DefineCapturedParameter(System.Int32 scope_id, System.String name, System.String captured_name) : System.Void`  
- `public DefineCapturedScope(System.Int32 scope_id, System.Int32 id, System.String captured_name) : System.Void`  
- `public DefineCapturedThis(System.Int32 scope_id, System.String captured_name) : System.Void`  
- `public DefineCompilationUnit(Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry source) : Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry`  
- `public DefineDocument(System.String url) : Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry`  
- `public DefineDocument(System.String url, System.Byte[] guid, System.Byte[] checksum) : Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry`  
- `public DefineLocalVariable(System.Int32 index, System.String name) : System.Void`  
- `public DefineNamespace(System.String name, Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry unit, System.String[] using_clauses, System.Int32 parent) : System.Int32`  
- `public DefineScopeVariable(System.Int32 scope, System.Int32 index) : System.Void`  
- `public EndIteratorBody(System.Int32 end_offset) : System.Void`  
- `public EndIteratorDispatcher(System.Int32 end_offset) : System.Void`  
- `public MarkSequencePoint(System.Int32 offset, Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry file, System.Int32 line, System.Int32 column, System.Boolean is_hidden) : System.Void`  
- `public OpenCompilerGeneratedBlock(System.Int32 start_offset) : System.Void`  
- `public OpenMethod(Colossal.Mono.CompilerServices.SymbolWriter.ICompileUnit file, System.Int32 ns_id, Colossal.Mono.CompilerServices.SymbolWriter.IMethodDef method) : Colossal.Mono.CompilerServices.SymbolWriter.SourceMethodBuilder`  
- `public OpenScope(System.Int32 start_offset) : System.Int32`  
- `public StartIteratorBody(System.Int32 start_offset) : System.Void`  
- `public StartIteratorDispatcher(System.Int32 start_offset) : System.Void`  
- `public WriteSymbolFile(System.Guid guid) : System.Void`  

