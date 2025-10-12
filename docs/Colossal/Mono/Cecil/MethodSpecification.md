# Colossal.Mono.Cecil.MethodSpecification

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class abstract public  

**Base:** `Colossal.Mono.Cecil.MethodReference`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`, `Colossal.Mono.Cecil.IMethodSignature`, `Colossal.Mono.Cecil.IGenericParameterProvider`, `Colossal.Mono.Cecil.IGenericContext`  

## Fields

- `private readonly Colossal.Mono.Cecil.MethodReference method`  

## Properties

- `public Colossal.Mono.Cecil.MethodReference ElementMethod { get }`  
- `public System.String Name { get; set }`  
- `public Colossal.Mono.Cecil.MethodCallingConvention CallingConvention { get; set }`  
- `public System.Boolean HasThis { get; set }`  
- `public System.Boolean ExplicitThis { get; set }`  
- `public Colossal.Mono.Cecil.MethodReturnType MethodReturnType { get; set }`  
- `public Colossal.Mono.Cecil.TypeReference DeclaringType { get; set }`  
- `public Colossal.Mono.Cecil.ModuleDefinition Module { get }`  
- `public System.Boolean HasParameters { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ParameterDefinition> Parameters { get }`  
- `public System.Boolean ContainsGenericParameter { get }`  

## Constructors

- `internal MethodSpecification(Colossal.Mono.Cecil.MethodReference method)`  

## Methods

- `public GetElementMethod() : Colossal.Mono.Cecil.MethodReference`  

