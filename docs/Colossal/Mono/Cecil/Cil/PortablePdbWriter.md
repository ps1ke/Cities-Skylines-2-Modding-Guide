# Colossal.Mono.Cecil.Cil.PortablePdbWriter

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.Cil.ISymbolWriter`, `System.IDisposable`  

## Fields

- `private readonly Colossal.Mono.Cecil.MetadataBuilder pdb_metadata`  
- `private readonly Colossal.Mono.Cecil.ModuleDefinition module`  
- `private readonly Colossal.Mono.Cecil.PE.ImageWriter writer`  
- `private Colossal.Mono.Cecil.MetadataBuilder module_metadata`  

## Properties

- `private System.Boolean IsEmbedded { private get }`  

## Constructors

- `internal PortablePdbWriter(Colossal.Mono.Cecil.MetadataBuilder pdb_metadata, Colossal.Mono.Cecil.ModuleDefinition module)`  
- `internal PortablePdbWriter(Colossal.Mono.Cecil.MetadataBuilder pdb_metadata, Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.Cecil.PE.ImageWriter writer)`  

## Methods

- `private CheckMethodDebugInformationTable() : System.Void`  
- `public Dispose() : System.Void`  
- `public GetDebugHeader() : Colossal.Mono.Cecil.Cil.ImageDebugHeader`  
- `public GetReaderProvider() : Colossal.Mono.Cecil.Cil.ISymbolReaderProvider`  
- `public Write(Colossal.Mono.Cecil.Cil.MethodDebugInformation info) : System.Void`  
- `private WritePdbFile() : System.Void`  
- `private WritePdbHeap() : System.Void`  
- `private WriteTableHeap() : System.Void`  

