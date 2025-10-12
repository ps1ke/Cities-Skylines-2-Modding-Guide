# Colossal.Mono.Cecil.GenericParameter

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.TypeReference`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`, `Colossal.Mono.Cecil.IGenericParameterProvider`, `Colossal.Mono.Cecil.IGenericContext`, `Colossal.Mono.Cecil.ICustomAttributeProvider`  

## Fields

- `internal System.Int32 position`  
- `internal Colossal.Mono.Cecil.GenericParameterType type`  
- `internal Colossal.Mono.Cecil.IGenericParameterProvider owner`  
- `private System.UInt16 attributes`  
- `private Colossal.Mono.Cecil.GenericParameterConstraintCollection constraints`  
- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> custom_attributes`  

## Properties

- `public Colossal.Mono.Cecil.GenericParameterAttributes Attributes { get; set }`  
- `public System.Int32 Position { get }`  
- `public Colossal.Mono.Cecil.GenericParameterType Type { get }`  
- `public Colossal.Mono.Cecil.IGenericParameterProvider Owner { get }`  
- `public System.Boolean HasConstraints { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.GenericParameterConstraint> Constraints { get }`  
- `public System.Boolean HasCustomAttributes { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get }`  
- `public Colossal.Mono.Cecil.IMetadataScope Scope { get; set }`  
- `public Colossal.Mono.Cecil.TypeReference DeclaringType { get; set }`  
- `public Colossal.Mono.Cecil.MethodReference DeclaringMethod { get }`  
- `public Colossal.Mono.Cecil.ModuleDefinition Module { get }`  
- `public System.String Name { get }`  
- `public System.String Namespace { get; set }`  
- `public System.String FullName { get }`  
- `public System.Boolean IsGenericParameter { get }`  
- `public System.Boolean ContainsGenericParameter { get }`  
- `public Colossal.Mono.Cecil.MetadataType MetadataType { get }`  
- `public System.Boolean IsNonVariant { get; set }`  
- `public System.Boolean IsCovariant { get; set }`  
- `public System.Boolean IsContravariant { get; set }`  
- `public System.Boolean HasReferenceTypeConstraint { get; set }`  
- `public System.Boolean HasNotNullableValueTypeConstraint { get; set }`  
- `public System.Boolean HasDefaultConstructorConstraint { get; set }`  

## Constructors

- `public GenericParameter(Colossal.Mono.Cecil.IGenericParameterProvider owner)`  
- `public GenericParameter(System.String name, Colossal.Mono.Cecil.IGenericParameterProvider owner)`  
- `internal GenericParameter(System.Int32 position, Colossal.Mono.Cecil.GenericParameterType type, Colossal.Mono.Cecil.ModuleDefinition module)`  

## Methods

- `private static ConvertGenericParameterType(Colossal.Mono.Cecil.GenericParameterType type) : Colossal.Mono.Cecil.Metadata.ElementType`  
- `public virtual Resolve() : Colossal.Mono.Cecil.TypeDefinition`  

## Nested types

- `Colossal.Mono.Cecil.GenericParameter+<>c`  

