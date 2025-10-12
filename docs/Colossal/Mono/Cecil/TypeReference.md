# Colossal.Mono.Cecil.TypeReference

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class public  

**Base:** `Colossal.Mono.Cecil.MemberReference`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`, `Colossal.Mono.Cecil.IGenericParameterProvider`, `Colossal.Mono.Cecil.IGenericContext`  

## Fields

- `private System.String namespace`  
- `private System.Boolean value_type`  
- `internal Colossal.Mono.Cecil.IMetadataScope scope`  
- `internal Colossal.Mono.Cecil.ModuleDefinition module`  
- `internal Colossal.Mono.Cecil.Metadata.ElementType etype`  
- `private System.String fullname`  
- `protected Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.GenericParameter> generic_parameters`  

## Properties

- `public System.String Name { get; set }`  
- `public System.String Namespace { get; set }`  
- `public System.Boolean IsValueType { get; set }`  
- `public Colossal.Mono.Cecil.ModuleDefinition Module { get }`  
- `internal Colossal.Mono.Cecil.TypeReferenceProjection WindowsRuntimeProjection { internal get; internal set }`  
- `private Colossal.Mono.Cecil.IGenericParameterProvider Colossal.Mono.Cecil.IGenericContext.Type { private get }`  
- `private Colossal.Mono.Cecil.IGenericParameterProvider Colossal.Mono.Cecil.IGenericContext.Method { private get }`  
- `private Colossal.Mono.Cecil.GenericParameterType Colossal.Mono.Cecil.IGenericParameterProvider.GenericParameterType { private get }`  
- `public System.Boolean HasGenericParameters { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.GenericParameter> GenericParameters { get }`  
- `public Colossal.Mono.Cecil.IMetadataScope Scope { get; set }`  
- `public System.Boolean IsNested { get }`  
- `public Colossal.Mono.Cecil.TypeReference DeclaringType { get; set }`  
- `public System.String FullName { get }`  
- `public System.Boolean IsByReference { get }`  
- `public System.Boolean IsPointer { get }`  
- `public System.Boolean IsSentinel { get }`  
- `public System.Boolean IsArray { get }`  
- `public System.Boolean IsGenericParameter { get }`  
- `public System.Boolean IsGenericInstance { get }`  
- `public System.Boolean IsRequiredModifier { get }`  
- `public System.Boolean IsOptionalModifier { get }`  
- `public System.Boolean IsPinned { get }`  
- `public System.Boolean IsFunctionPointer { get }`  
- `public System.Boolean IsPrimitive { get }`  
- `public Colossal.Mono.Cecil.MetadataType MetadataType { get }`  

## Constructors

- `protected TypeReference(System.String namespace, System.String name)`  
- `public TypeReference(System.String namespace, System.String name, Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.Cecil.IMetadataScope scope)`  
- `public TypeReference(System.String namespace, System.String name, Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.Cecil.IMetadataScope scope, System.Boolean valueType)`  

## Methods

- `protected virtual ClearFullName() : System.Void`  
- `public virtual GetElementType() : Colossal.Mono.Cecil.TypeReference`  
- `public virtual Resolve() : Colossal.Mono.Cecil.TypeDefinition`  
- `protected virtual ResolveDefinition() : Colossal.Mono.Cecil.IMemberDefinition`  

