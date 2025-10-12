# Colossal.Mono.Cecil.ParameterDefinition

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.ParameterReference`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`, `Colossal.Mono.Cecil.ICustomAttributeProvider`, `Colossal.Mono.Cecil.IConstantProvider`, `Colossal.Mono.Cecil.IMarshalInfoProvider`  

## Fields

- `private System.UInt16 attributes`  
- `internal Colossal.Mono.Cecil.IMethodSignature method`  
- `private System.Object constant`  
- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> custom_attributes`  
- `private Colossal.Mono.Cecil.MarshalInfo marshal_info`  

## Properties

- `public Colossal.Mono.Cecil.ParameterAttributes Attributes { get; set }`  
- `public Colossal.Mono.Cecil.IMethodSignature Method { get }`  
- `public System.Int32 Sequence { get }`  
- `public System.Boolean HasConstant { get; set }`  
- `public System.Object Constant { get; set }`  
- `public System.Boolean HasCustomAttributes { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get }`  
- `public System.Boolean HasMarshalInfo { get }`  
- `public Colossal.Mono.Cecil.MarshalInfo MarshalInfo { get; set }`  
- `public System.Boolean IsIn { get; set }`  
- `public System.Boolean IsOut { get; set }`  
- `public System.Boolean IsLcid { get; set }`  
- `public System.Boolean IsReturnValue { get; set }`  
- `public System.Boolean IsOptional { get; set }`  
- `public System.Boolean HasDefault { get; set }`  
- `public System.Boolean HasFieldMarshal { get; set }`  

## Constructors

- `internal ParameterDefinition(Colossal.Mono.Cecil.TypeReference parameterType, Colossal.Mono.Cecil.IMethodSignature method)`  
- `public ParameterDefinition(Colossal.Mono.Cecil.TypeReference parameterType)`  
- `public ParameterDefinition(System.String name, Colossal.Mono.Cecil.ParameterAttributes attributes, Colossal.Mono.Cecil.TypeReference parameterType)`  

## Methods

- `public virtual Resolve() : Colossal.Mono.Cecil.ParameterDefinition`  

