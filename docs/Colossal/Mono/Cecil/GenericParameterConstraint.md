# Colossal.Mono.Cecil.GenericParameterConstraint

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.ICustomAttributeProvider`, `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Fields

- `internal Colossal.Mono.Cecil.GenericParameter generic_parameter`  
- `internal Colossal.Mono.Cecil.MetadataToken token`  
- `private Colossal.Mono.Cecil.TypeReference constraint_type`  
- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> custom_attributes`  

## Properties

- `public Colossal.Mono.Cecil.TypeReference ConstraintType { get; set }`  
- `public System.Boolean HasCustomAttributes { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get }`  
- `public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set }`  

## Constructors

- `internal GenericParameterConstraint(Colossal.Mono.Cecil.TypeReference constraintType, Colossal.Mono.Cecil.MetadataToken token)`  
- `public GenericParameterConstraint(Colossal.Mono.Cecil.TypeReference constraintType)`  

