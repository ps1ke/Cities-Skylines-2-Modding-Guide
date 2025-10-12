# Colossal.Mono.CompilerServices.SymbolWriter.SourceMethodBuilder

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.CompilerServices.SymbolWriter`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.LocalVariableEntry> _locals`  
- `private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry> _blocks`  
- `private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.ScopeVariable> _scope_vars`  
- `private System.Collections.Generic.Stack<Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry> _block_stack`  
- `private readonly System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.LineNumberEntry> method_lines`  
- `private readonly Colossal.Mono.CompilerServices.SymbolWriter.ICompileUnit _comp_unit`  
- `private readonly System.Int32 ns_id`  
- `private readonly Colossal.Mono.CompilerServices.SymbolWriter.IMethodDef method`  

## Properties

- `public Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry[] Blocks { get }`  
- `public Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry CurrentBlock { get }`  
- `public Colossal.Mono.CompilerServices.SymbolWriter.LocalVariableEntry[] Locals { get }`  
- `public Colossal.Mono.CompilerServices.SymbolWriter.ICompileUnit SourceFile { get }`  
- `public Colossal.Mono.CompilerServices.SymbolWriter.ScopeVariable[] ScopeVariables { get }`  

## Constructors

- `public SourceMethodBuilder(Colossal.Mono.CompilerServices.SymbolWriter.ICompileUnit comp_unit)`  
- `public SourceMethodBuilder(Colossal.Mono.CompilerServices.SymbolWriter.ICompileUnit comp_unit, System.Int32 ns_id, Colossal.Mono.CompilerServices.SymbolWriter.IMethodDef method)`  

## Methods

- `public AddLocal(System.Int32 index, System.String name) : System.Void`  
- `public AddScopeVariable(System.Int32 scope, System.Int32 index) : System.Void`  
- `public DefineMethod(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file) : System.Void`  
- `public DefineMethod(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, System.Int32 token) : System.Void`  
- `public EndBlock(System.Int32 end_offset) : System.Void`  
- `public MarkSequencePoint(System.Int32 offset, Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry file, System.Int32 line, System.Int32 column, System.Boolean is_hidden) : System.Void`  
- `public MarkSequencePoint(System.Int32 offset, Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry file, System.Int32 line, System.Int32 column, System.Int32 end_line, System.Int32 end_column, System.Boolean is_hidden) : System.Void`  
- `public StartBlock(Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry+Type type, System.Int32 start_offset) : System.Void`  
- `public StartBlock(Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry+Type type, System.Int32 start_offset, System.Int32 scopeIndex) : System.Void`  

