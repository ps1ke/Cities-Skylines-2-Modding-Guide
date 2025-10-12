# Colossal.Mono.Cecil.TypeSpecification

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class abstract public  

**Base:** `Colossal.Mono.Cecil.TypeReference`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`, `Colossal.Mono.Cecil.IGenericParameterProvider`, `Colossal.Mono.Cecil.IGenericContext`  

## Fields

- `private readonly Colossal.Mono.Cecil.TypeReference element_type`  

## Properties

- `public Colossal.Mono.Cecil.TypeReference ElementType { get }`  
- `public System.String Name { get; set }`  
- `public System.String Namespace { get; set }`  
- `public Colossal.Mono.Cecil.IMetadataScope Scope { get; set }`  
- `public Colossal.Mono.Cecil.ModuleDefinition Module { get }`  
- `public System.String FullName { get }`  
- `public System.Boolean ContainsGenericParameter { get }`  
- `public Colossal.Mono.Cecil.MetadataType MetadataType { get }`  

## Constructors

- `internal TypeSpecification(Colossal.Mono.Cecil.TypeReference type)`  

## Methods

- `public virtual GetElementType() : Colossal.Mono.Cecil.TypeReference`  

