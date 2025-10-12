# Colossal.Mono.Cecil.InterfaceImplementation

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.ICustomAttributeProvider`, `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Fields

- `internal Colossal.Mono.Cecil.TypeDefinition type`  
- `internal Colossal.Mono.Cecil.MetadataToken token`  
- `private Colossal.Mono.Cecil.TypeReference interface_type`  
- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> custom_attributes`  

## Properties

- `public Colossal.Mono.Cecil.TypeReference InterfaceType { get; set }`  
- `public System.Boolean HasCustomAttributes { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get }`  
- `public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set }`  

## Constructors

- `internal InterfaceImplementation(Colossal.Mono.Cecil.TypeReference interfaceType, Colossal.Mono.Cecil.MetadataToken token)`  
- `public InterfaceImplementation(Colossal.Mono.Cecil.TypeReference interfaceType)`  

