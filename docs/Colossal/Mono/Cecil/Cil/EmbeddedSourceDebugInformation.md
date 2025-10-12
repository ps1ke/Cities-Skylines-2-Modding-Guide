# Colossal.Mono.Cecil.Cil.EmbeddedSourceDebugInformation

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.Cil.CustomDebugInformation`  
**Implements:** `Colossal.Mono.Cecil.Cil.ICustomDebugInformationProvider`, `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Fields

- `internal System.UInt32 index`  
- `internal Colossal.Mono.Cecil.MetadataReader debug_reader`  
- `internal System.Boolean resolved`  
- `internal System.Byte[] content`  
- `internal System.Boolean compress`  
- `public static System.Guid KindIdentifier`  

## Properties

- `public System.Byte[] Content { get; set }`  
- `public System.Boolean Compress { get; set }`  
- `public Colossal.Mono.Cecil.Cil.CustomDebugInformationKind Kind { get }`  

## Constructors

- `internal EmbeddedSourceDebugInformation(System.UInt32 index, Colossal.Mono.Cecil.MetadataReader debug_reader)`  
- `public EmbeddedSourceDebugInformation(System.Byte[] content, System.Boolean compress)`  

## Methods

- `internal ReadRawEmbeddedSourceDebugInformation() : System.Byte[]`  
- `private Resolve() : System.Void`  

