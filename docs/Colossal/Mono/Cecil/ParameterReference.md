# Colossal.Mono.Cecil.ParameterReference

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Fields

- `private System.String name`  
- `internal System.Int32 index`  
- `protected Colossal.Mono.Cecil.TypeReference parameter_type`  
- `internal Colossal.Mono.Cecil.MetadataToken token`  

## Properties

- `public System.String Name { get; set }`  
- `public System.Int32 Index { get }`  
- `public Colossal.Mono.Cecil.TypeReference ParameterType { get; set }`  
- `public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set }`  

## Constructors

- `internal ParameterReference(System.String name, Colossal.Mono.Cecil.TypeReference parameterType)`  

## Methods

- `public abstract Resolve() : Colossal.Mono.Cecil.ParameterDefinition`  
- `public virtual ToString() : System.String`  

