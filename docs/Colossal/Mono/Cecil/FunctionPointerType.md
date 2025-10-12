# Colossal.Mono.Cecil.FunctionPointerType

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.TypeSpecification`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`, `Colossal.Mono.Cecil.IGenericParameterProvider`, `Colossal.Mono.Cecil.IGenericContext`, `Colossal.Mono.Cecil.IMethodSignature`  

## Fields

- `private readonly Colossal.Mono.Cecil.MethodReference function`  

## Properties

- `public System.Boolean HasThis { get; set }`  
- `public System.Boolean ExplicitThis { get; set }`  
- `public Colossal.Mono.Cecil.MethodCallingConvention CallingConvention { get; set }`  
- `public System.Boolean HasParameters { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ParameterDefinition> Parameters { get }`  
- `public Colossal.Mono.Cecil.TypeReference ReturnType { get; set }`  
- `public Colossal.Mono.Cecil.MethodReturnType MethodReturnType { get }`  
- `public System.String Name { get; set }`  
- `public System.String Namespace { get; set }`  
- `public Colossal.Mono.Cecil.ModuleDefinition Module { get }`  
- `public Colossal.Mono.Cecil.IMetadataScope Scope { get; set }`  
- `public System.Boolean IsFunctionPointer { get }`  
- `public System.Boolean ContainsGenericParameter { get }`  
- `public System.String FullName { get }`  

## Constructors

- `public FunctionPointerType()`  

## Methods

- `public virtual GetElementType() : Colossal.Mono.Cecil.TypeReference`  
- `public virtual Resolve() : Colossal.Mono.Cecil.TypeDefinition`  

