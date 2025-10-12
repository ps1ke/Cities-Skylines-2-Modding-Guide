# Colossal.Mono.Cecil.EmbeddedResource

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.Resource`  

## Fields

- `private readonly Colossal.Mono.Cecil.MetadataReader reader`  
- `private System.Nullable<System.UInt32> offset`  
- `private System.Byte[] data`  
- `private System.IO.Stream stream`  

## Properties

- `public Colossal.Mono.Cecil.ResourceType ResourceType { get }`  

## Constructors

- `public EmbeddedResource(System.String name, Colossal.Mono.Cecil.ManifestResourceAttributes attributes, System.Byte[] data)`  
- `public EmbeddedResource(System.String name, Colossal.Mono.Cecil.ManifestResourceAttributes attributes, System.IO.Stream stream)`  
- `internal EmbeddedResource(System.String name, Colossal.Mono.Cecil.ManifestResourceAttributes attributes, System.UInt32 offset, Colossal.Mono.Cecil.MetadataReader reader)`  

## Methods

- `public GetResourceData() : System.Byte[]`  
- `public GetResourceStream() : System.IO.Stream`  
- `private static ReadStream(System.IO.Stream stream) : System.Byte[]`  

