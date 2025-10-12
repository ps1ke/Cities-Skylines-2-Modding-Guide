# Colossal.Mono.Cecil.CallSite

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.IMethodSignature`, `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Fields

- `private readonly Colossal.Mono.Cecil.MethodReference signature`  

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
- `public Colossal.Mono.Cecil.IMetadataScope Scope { get }`  
- `public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set }`  
- `public System.String FullName { get }`  

## Constructors

- `internal CallSite()`  
- `public CallSite(Colossal.Mono.Cecil.TypeReference returnType)`  

## Methods

- `public virtual ToString() : System.String`  

