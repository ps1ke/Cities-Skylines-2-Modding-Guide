# Colossal.Mono.Cecil.MethodReturnType

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.IConstantProvider`, `Colossal.Mono.Cecil.IMetadataTokenProvider`, `Colossal.Mono.Cecil.ICustomAttributeProvider`, `Colossal.Mono.Cecil.IMarshalInfoProvider`  

## Fields

- `internal Colossal.Mono.Cecil.IMethodSignature method`  
- `internal Colossal.Mono.Cecil.ParameterDefinition parameter`  
- `private Colossal.Mono.Cecil.TypeReference return_type`  

## Properties

- `public Colossal.Mono.Cecil.IMethodSignature Method { get }`  
- `public Colossal.Mono.Cecil.TypeReference ReturnType { get; set }`  
- `internal Colossal.Mono.Cecil.ParameterDefinition Parameter { internal get }`  
- `public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set }`  
- `public Colossal.Mono.Cecil.ParameterAttributes Attributes { get; set }`  
- `public System.String Name { get; set }`  
- `public System.Boolean HasCustomAttributes { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get }`  
- `public System.Boolean HasDefault { get; set }`  
- `public System.Boolean HasConstant { get; set }`  
- `public System.Object Constant { get; set }`  
- `public System.Boolean HasFieldMarshal { get; set }`  
- `public System.Boolean HasMarshalInfo { get }`  
- `public Colossal.Mono.Cecil.MarshalInfo MarshalInfo { get; set }`  

## Constructors

- `public MethodReturnType(Colossal.Mono.Cecil.IMethodSignature method)`  

