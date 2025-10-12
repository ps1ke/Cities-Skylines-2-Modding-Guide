# Colossal.Mono.Cecil.DefaultMetadataImporter

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.IMetadataImporter`  

## Fields

- `protected readonly Colossal.Mono.Cecil.ModuleDefinition module`  

## Constructors

- `public DefaultMetadataImporter(Colossal.Mono.Cecil.ModuleDefinition module)`  

## Methods

- `private ImportField(Colossal.Mono.Cecil.FieldReference field, Colossal.Mono.Cecil.ImportGenericContext context) : Colossal.Mono.Cecil.FieldReference`  
- `private static ImportGenericParameters(Colossal.Mono.Cecil.IGenericParameterProvider imported, Colossal.Mono.Cecil.IGenericParameterProvider original) : System.Void`  
- `private ImportMethod(Colossal.Mono.Cecil.MethodReference method, Colossal.Mono.Cecil.ImportGenericContext context) : Colossal.Mono.Cecil.MethodReference`  
- `private ImportMethodSpecification(Colossal.Mono.Cecil.MethodReference method, Colossal.Mono.Cecil.ImportGenericContext context) : Colossal.Mono.Cecil.MethodSpecification`  
- `public virtual ImportReference(Colossal.Mono.Cecil.AssemblyNameReference name) : Colossal.Mono.Cecil.AssemblyNameReference`  
- `public virtual ImportReference(Colossal.Mono.Cecil.TypeReference type, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.TypeReference`  
- `public virtual ImportReference(Colossal.Mono.Cecil.FieldReference field, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.FieldReference`  
- `public virtual ImportReference(Colossal.Mono.Cecil.MethodReference method, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.MethodReference`  
- `protected virtual ImportScope(Colossal.Mono.Cecil.TypeReference type) : Colossal.Mono.Cecil.IMetadataScope`  
- `protected ImportScope(Colossal.Mono.Cecil.IMetadataScope scope) : Colossal.Mono.Cecil.IMetadataScope`  
- `private ImportType(Colossal.Mono.Cecil.TypeReference type, Colossal.Mono.Cecil.ImportGenericContext context) : Colossal.Mono.Cecil.TypeReference`  
- `private ImportTypeSpecification(Colossal.Mono.Cecil.TypeReference type, Colossal.Mono.Cecil.ImportGenericContext context) : Colossal.Mono.Cecil.TypeReference`  

