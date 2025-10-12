# Colossal.Mono.Cecil.Cil.PortablePdbReader

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.Cil.ISymbolReader`, `System.IDisposable`  

## Fields

- `private readonly Colossal.Mono.Cecil.PE.Image image`  
- `private readonly Colossal.Mono.Cecil.ModuleDefinition module`  
- `private readonly Colossal.Mono.Cecil.MetadataReader reader`  
- `private readonly Colossal.Mono.Cecil.MetadataReader debug_reader`  

## Properties

- `private System.Boolean IsEmbedded { private get }`  

## Constructors

- `internal PortablePdbReader(Colossal.Mono.Cecil.PE.Image image, Colossal.Mono.Cecil.ModuleDefinition module)`  

## Methods

- `public Dispose() : System.Void`  
- `public GetWriterProvider() : Colossal.Mono.Cecil.Cil.ISymbolWriterProvider`  
- `private static IsMatchingEntry(Colossal.Mono.Cecil.Metadata.PdbHeap heap, Colossal.Mono.Cecil.Cil.ImageDebugHeaderEntry entry) : System.Boolean`  
- `public ProcessDebugHeader(Colossal.Mono.Cecil.Cil.ImageDebugHeader header) : System.Boolean`  
- `public Read(Colossal.Mono.Cecil.MethodDefinition method) : Colossal.Mono.Cecil.Cil.MethodDebugInformation`  
- `private ReadCustomDebugInformations(Colossal.Mono.Cecil.Cil.MethodDebugInformation info) : System.Void`  
- `private static ReadInt32(System.Byte[] bytes, System.Int32 start) : System.Int32`  
- `private ReadModule() : System.Void`  
- `private ReadScope(Colossal.Mono.Cecil.Cil.MethodDebugInformation method_info) : System.Void`  
- `private ReadSequencePoints(Colossal.Mono.Cecil.Cil.MethodDebugInformation method_info) : System.Void`  
- `private ReadStateMachineKickOffMethod(Colossal.Mono.Cecil.Cil.MethodDebugInformation method_info) : System.Void`  

