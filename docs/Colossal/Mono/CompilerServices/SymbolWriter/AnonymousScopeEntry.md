# Colossal.Mono.CompilerServices.SymbolWriter.AnonymousScopeEntry

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.CompilerServices.SymbolWriter`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `public readonly System.Int32 ID`  
- `private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.CapturedVariable> captured_vars`  
- `private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.CapturedScope> captured_scopes`  

## Properties

- `public Colossal.Mono.CompilerServices.SymbolWriter.CapturedVariable[] CapturedVariables { get }`  
- `public Colossal.Mono.CompilerServices.SymbolWriter.CapturedScope[] CapturedScopes { get }`  

## Constructors

- `public AnonymousScopeEntry(System.Int32 id)`  
- `internal AnonymousScopeEntry(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader)`  

## Methods

- `internal AddCapturedScope(System.Int32 scope, System.String captured_name) : System.Void`  
- `internal AddCapturedVariable(System.String name, System.String captured_name, Colossal.Mono.CompilerServices.SymbolWriter.CapturedVariable+CapturedKind kind) : System.Void`  
- `public virtual ToString() : System.String`  
- `internal Write(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryWriter bw) : System.Void`  

