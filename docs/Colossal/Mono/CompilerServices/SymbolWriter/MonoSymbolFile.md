# Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.CompilerServices.SymbolWriter`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Fields

- `private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry> methods`  
- `private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry> sources`  
- `private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry> comp_units`  
- `private System.Collections.Generic.Dictionary<System.Int32, Colossal.Mono.CompilerServices.SymbolWriter.AnonymousScopeEntry> anonymous_scopes`  
- `private Colossal.Mono.CompilerServices.SymbolWriter.OffsetTable ot`  
- `private System.Int32 last_type_index`  
- `private System.Int32 last_method_index`  
- `private System.Int32 last_namespace_index`  
- `public readonly System.Int32 MajorVersion`  
- `public readonly System.Int32 MinorVersion`  
- `public System.Int32 NumLineNumbers`  
- `private Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader`  
- `private System.Collections.Generic.Dictionary<System.Int32, Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry> source_file_hash`  
- `private System.Collections.Generic.Dictionary<System.Int32, Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry> compile_unit_hash`  
- `private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry> method_list`  
- `private System.Collections.Generic.Dictionary<System.Int32, Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry> method_token_hash`  
- `private System.Collections.Generic.Dictionary<System.String, System.Int32> source_name_hash`  
- `private System.Guid guid`  
- `internal System.Int32 LineNumberCount`  
- `internal System.Int32 LocalCount`  
- `internal System.Int32 StringSize`  
- `internal System.Int32 LineNumberSize`  
- `internal System.Int32 ExtendedLineNumberSize`  

## Properties

- `public System.Int32 CompileUnitCount { get }`  
- `public System.Int32 SourceCount { get }`  
- `public System.Int32 MethodCount { get }`  
- `public System.Int32 TypeCount { get }`  
- `public System.Int32 AnonymousScopeCount { get }`  
- `public System.Int32 NamespaceCount { get }`  
- `public System.Guid Guid { get }`  
- `public Colossal.Mono.CompilerServices.SymbolWriter.OffsetTable OffsetTable { get }`  
- `public Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry[] Sources { get }`  
- `public Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry[] CompileUnits { get }`  
- `public Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry[] Methods { get }`  
- `internal Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader BinaryReader { internal get }`  

## Constructors

- `public MonoSymbolFile()`  
- `private MonoSymbolFile(System.IO.Stream stream)`  

## Methods

- `public AddCompileUnit(Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry entry) : System.Int32`  
- `public AddMethod(Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry entry) : System.Void`  
- `public AddSource(Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry source) : System.Int32`  
- `public CreateSymbolFile(System.Guid guid, System.IO.FileStream fs) : System.Void`  
- `internal DefineAnonymousScope(System.Int32 id) : System.Void`  
- `internal DefineCapturedScope(System.Int32 scope_id, System.Int32 id, System.String captured_name) : System.Void`  
- `internal DefineCapturedVariable(System.Int32 scope_id, System.String name, System.String captured_name, Colossal.Mono.CompilerServices.SymbolWriter.CapturedVariable+CapturedKind kind) : System.Void`  
- `public DefineMethod(Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry comp_unit, System.Int32 token, Colossal.Mono.CompilerServices.SymbolWriter.ScopeVariable[] scope_vars, Colossal.Mono.CompilerServices.SymbolWriter.LocalVariableEntry[] locals, Colossal.Mono.CompilerServices.SymbolWriter.LineNumberEntry[] lines, Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry[] code_blocks, System.String real_name, Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry+Flags flags, System.Int32 namespace_id) : Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry`  
- `public Dispose() : System.Void`  
- `protected virtual Dispose(System.Boolean disposing) : System.Void`  
- `public FindSource(System.String file_name) : System.Int32`  
- `public GetAnonymousScope(System.Int32 id) : Colossal.Mono.CompilerServices.SymbolWriter.AnonymousScopeEntry`  
- `public GetCompileUnit(System.Int32 index) : Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry`  
- `public GetMethod(System.Int32 index) : Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry`  
- `public GetMethodByToken(System.Int32 token) : Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry`  
- `internal GetNextMethodIndex() : System.Int32`  
- `internal GetNextNamespaceIndex() : System.Int32`  
- `internal GetNextTypeIndex() : System.Int32`  
- `public GetSourceFile(System.Int32 index) : Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry`  
- `private read_methods() : System.Void`  
- `public static ReadSymbolFile(System.Reflection.Assembly assembly) : Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile`  
- `public static ReadSymbolFile(System.String mdbFilename) : Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile`  
- `public static ReadSymbolFile(System.String mdbFilename, System.Guid assemblyGuid) : Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile`  
- `public static ReadSymbolFile(System.IO.Stream stream) : Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile`  
- `private Write(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryWriter bw, System.Guid guid) : System.Void`  

