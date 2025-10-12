# Colossal.Mono.Cecil.MethodReference

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class public  

**Base:** `Colossal.Mono.Cecil.MemberReference`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`, `Colossal.Mono.Cecil.IMethodSignature`, `Colossal.Mono.Cecil.IGenericParameterProvider`, `Colossal.Mono.Cecil.IGenericContext`  

## Fields

- `internal Colossal.Mono.Cecil.ParameterDefinitionCollection parameters`  
- `private Colossal.Mono.Cecil.MethodReturnType return_type`  
- `private System.Boolean has_this`  
- `private System.Boolean explicit_this`  
- `private Colossal.Mono.Cecil.MethodCallingConvention calling_convention`  
- `internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.GenericParameter> generic_parameters`  

## Properties

- `public System.Boolean HasThis { get; set }`  
- `public System.Boolean ExplicitThis { get; set }`  
- `public Colossal.Mono.Cecil.MethodCallingConvention CallingConvention { get; set }`  
- `public System.Boolean HasParameters { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ParameterDefinition> Parameters { get }`  
- `private Colossal.Mono.Cecil.IGenericParameterProvider Colossal.Mono.Cecil.IGenericContext.Type { private get }`  
- `private Colossal.Mono.Cecil.IGenericParameterProvider Colossal.Mono.Cecil.IGenericContext.Method { private get }`  
- `private Colossal.Mono.Cecil.GenericParameterType Colossal.Mono.Cecil.IGenericParameterProvider.GenericParameterType { private get }`  
- `public System.Boolean HasGenericParameters { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.GenericParameter> GenericParameters { get }`  
- `public Colossal.Mono.Cecil.TypeReference ReturnType { get; set }`  
- `public Colossal.Mono.Cecil.MethodReturnType MethodReturnType { get; set }`  
- `public System.String FullName { get }`  
- `public System.Boolean IsGenericInstance { get }`  
- `public System.Boolean ContainsGenericParameter { get }`  

## Constructors

- `internal MethodReference()`  
- `public MethodReference(System.String name, Colossal.Mono.Cecil.TypeReference returnType)`  
- `public MethodReference(System.String name, Colossal.Mono.Cecil.TypeReference returnType, Colossal.Mono.Cecil.TypeReference declaringType)`  

## Methods

- `public virtual GetElementMethod() : Colossal.Mono.Cecil.MethodReference`  
- `public virtual Resolve() : Colossal.Mono.Cecil.MethodDefinition`  
- `protected virtual ResolveDefinition() : Colossal.Mono.Cecil.IMemberDefinition`  

