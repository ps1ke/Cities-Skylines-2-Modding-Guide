# Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.CompilerServices.SymbolWriter`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IComparable`  

## Fields

- `public readonly System.Int32 CompileUnitIndex`  
- `public readonly System.Int32 Token`  
- `public readonly System.Int32 NamespaceID`  
- `private System.Int32 DataOffset`  
- `private System.Int32 LocalVariableTableOffset`  
- `private System.Int32 LineNumberTableOffset`  
- `private System.Int32 CodeBlockTableOffset`  
- `private System.Int32 ScopeVariableTableOffset`  
- `private System.Int32 RealNameOffset`  
- `private Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry+Flags flags`  
- `private System.Int32 index`  
- `public readonly Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry CompileUnit`  
- `private Colossal.Mono.CompilerServices.SymbolWriter.LocalVariableEntry[] locals`  
- `private Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry[] code_blocks`  
- `private Colossal.Mono.CompilerServices.SymbolWriter.ScopeVariable[] scope_vars`  
- `private Colossal.Mono.CompilerServices.SymbolWriter.LineNumberTable lnt`  
- `private System.String real_name`  
- `public readonly Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile SymbolFile`  
- `public static const System.Int32 Size`  

## Properties

- `public Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry+Flags MethodFlags { get }`  
- `public System.Int32 Index { get; set }`  

## Constructors

- `internal MethodEntry(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader, System.Int32 index)`  
- `internal MethodEntry(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry comp_unit, System.Int32 token, Colossal.Mono.CompilerServices.SymbolWriter.ScopeVariable[] scope_vars, Colossal.Mono.CompilerServices.SymbolWriter.LocalVariableEntry[] locals, Colossal.Mono.CompilerServices.SymbolWriter.LineNumberEntry[] lines, Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry[] code_blocks, System.String real_name, Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry+Flags flags, System.Int32 namespace_id)`  

## Methods

- `private static CheckLineNumberTable(Colossal.Mono.CompilerServices.SymbolWriter.LineNumberEntry[] line_numbers) : System.Void`  
- `public CompareTo(System.Object obj) : System.Int32`  
- `public GetCodeBlocks() : Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry[]`  
- `public GetLineNumberTable() : Colossal.Mono.CompilerServices.SymbolWriter.LineNumberTable`  
- `public GetLocals() : Colossal.Mono.CompilerServices.SymbolWriter.LocalVariableEntry[]`  
- `public GetRealName() : System.String`  
- `public GetScopeVariables() : Colossal.Mono.CompilerServices.SymbolWriter.ScopeVariable[]`  
- `public ReadAll() : System.Void`  
- `public virtual ToString() : System.String`  
- `internal Write(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryWriter bw) : System.Void`  
- `internal WriteData(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryWriter bw) : System.Void`  

## Nested types

- `Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry+Flags`  

