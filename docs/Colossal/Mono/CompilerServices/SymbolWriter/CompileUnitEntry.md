# Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.CompilerServices.SymbolWriter`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.CompilerServices.SymbolWriter.ICompileUnit`  

## Fields

- `public readonly System.Int32 Index`  
- `private System.Int32 DataOffset`  
- `private Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file`  
- `private Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry source`  
- `private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry> include_files`  
- `private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.NamespaceEntry> namespaces`  
- `private System.Boolean creating`  

## Properties

- `public static System.Int32 Size { get }`  
- `private Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry Colossal.Mono.CompilerServices.SymbolWriter.ICompileUnit.Entry { private get }`  
- `public Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry SourceFile { get }`  
- `public Colossal.Mono.CompilerServices.SymbolWriter.NamespaceEntry[] Namespaces { get }`  
- `public Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry[] IncludeFiles { get }`  

## Constructors

- `public CompileUnitEntry(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry source)`  
- `internal CompileUnitEntry(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader)`  

## Methods

- `public AddFile(Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry file) : System.Void`  
- `public DefineNamespace(System.String name, System.String[] using_clauses, System.Int32 parent) : System.Int32`  
- `public ReadAll() : System.Void`  
- `private ReadData() : System.Void`  
- `internal Write(System.IO.BinaryWriter bw) : System.Void`  
- `internal WriteData(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryWriter bw) : System.Void`  

