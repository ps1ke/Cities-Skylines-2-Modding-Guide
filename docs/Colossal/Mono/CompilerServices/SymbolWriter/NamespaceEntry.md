# Colossal.Mono.CompilerServices.SymbolWriter.NamespaceEntry

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.CompilerServices.SymbolWriter`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `public readonly System.String Name`  
- `public readonly System.Int32 Index`  
- `public readonly System.Int32 Parent`  
- `public readonly System.String[] UsingClauses`  

## Constructors

- `public NamespaceEntry(System.String name, System.Int32 index, System.String[] using_clauses, System.Int32 parent)`  
- `internal NamespaceEntry(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader)`  

## Methods

- `public virtual ToString() : System.String`  
- `internal Write(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryWriter bw) : System.Void`  

