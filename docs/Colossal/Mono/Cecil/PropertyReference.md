# Colossal.Mono.Cecil.PropertyReference

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class abstract public  

**Base:** `Colossal.Mono.Cecil.MemberReference`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Fields

- `private Colossal.Mono.Cecil.TypeReference property_type`  

## Properties

- `public Colossal.Mono.Cecil.TypeReference PropertyType { get; set }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ParameterDefinition> Parameters { get }`  

## Constructors

- `internal PropertyReference(System.String name, Colossal.Mono.Cecil.TypeReference propertyType)`  

## Methods

- `public abstract Resolve() : Colossal.Mono.Cecil.PropertyDefinition`  
- `protected virtual ResolveDefinition() : Colossal.Mono.Cecil.IMemberDefinition`  

