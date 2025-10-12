# Colossal.Mono.Cecil.FieldReference

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class public  

**Base:** `Colossal.Mono.Cecil.MemberReference`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Fields

- `private Colossal.Mono.Cecil.TypeReference field_type`  

## Properties

- `public Colossal.Mono.Cecil.TypeReference FieldType { get; set }`  
- `public System.String FullName { get }`  
- `public System.Boolean ContainsGenericParameter { get }`  

## Constructors

- `internal FieldReference()`  
- `public FieldReference(System.String name, Colossal.Mono.Cecil.TypeReference fieldType)`  
- `public FieldReference(System.String name, Colossal.Mono.Cecil.TypeReference fieldType, Colossal.Mono.Cecil.TypeReference declaringType)`  

## Methods

- `public virtual Resolve() : Colossal.Mono.Cecil.FieldDefinition`  
- `protected virtual ResolveDefinition() : Colossal.Mono.Cecil.IMemberDefinition`  

