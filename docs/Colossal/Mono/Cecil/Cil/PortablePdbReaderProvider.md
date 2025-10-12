# Colossal.Mono.Cecil.Cil.PortablePdbReaderProvider

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.Cil.ISymbolReaderProvider`  

## Constructors

- `public PortablePdbReaderProvider()`  

## Methods

- `public GetSymbolReader(Colossal.Mono.Cecil.ModuleDefinition module, System.String fileName) : Colossal.Mono.Cecil.Cil.ISymbolReader`  
- `public GetSymbolReader(Colossal.Mono.Cecil.ModuleDefinition module, System.IO.Stream symbolStream) : Colossal.Mono.Cecil.Cil.ISymbolReader`  
- `private GetSymbolReader(Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.Disposable<System.IO.Stream> symbolStream, System.String fileName) : Colossal.Mono.Cecil.Cil.ISymbolReader`  

