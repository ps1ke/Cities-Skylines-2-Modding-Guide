# Colossal.Mono.Cecil.PropertyDefinition

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.PropertyReference`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`, `Colossal.Mono.Cecil.IMemberDefinition`, `Colossal.Mono.Cecil.ICustomAttributeProvider`, `Colossal.Mono.Cecil.IConstantProvider`  

## Fields

- `private System.Nullable<System.Boolean> has_this`  
- `private System.UInt16 attributes`  
- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> custom_attributes`  
- `internal Colossal.Mono.Cecil.MethodDefinition get_method`  
- `internal Colossal.Mono.Cecil.MethodDefinition set_method`  
- `internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodDefinition> other_methods`  
- `private System.Object constant`  

## Properties

- `public Colossal.Mono.Cecil.PropertyAttributes Attributes { get; set }`  
- `public System.Boolean HasThis { get; set }`  
- `public System.Boolean HasCustomAttributes { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get }`  
- `public Colossal.Mono.Cecil.MethodDefinition GetMethod { get; set }`  
- `public Colossal.Mono.Cecil.MethodDefinition SetMethod { get; set }`  
- `public System.Boolean HasOtherMethods { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodDefinition> OtherMethods { get }`  
- `public System.Boolean HasParameters { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ParameterDefinition> Parameters { get }`  
- `public System.Boolean HasConstant { get; set }`  
- `public System.Object Constant { get; set }`  
- `public System.Boolean IsSpecialName { get; set }`  
- `public System.Boolean IsRuntimeSpecialName { get; set }`  
- `public System.Boolean HasDefault { get; set }`  
- `public Colossal.Mono.Cecil.TypeDefinition DeclaringType { get; set }`  
- `public System.Boolean IsDefinition { get }`  
- `public System.String FullName { get }`  

## Constructors

- `public PropertyDefinition(System.String name, Colossal.Mono.Cecil.PropertyAttributes attributes, Colossal.Mono.Cecil.TypeReference propertyType)`  

## Methods

- `private InitializeMethods() : System.Void`  
- `private static MirrorParameters(Colossal.Mono.Cecil.MethodDefinition method, System.Int32 bound) : Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ParameterDefinition>`  
- `public virtual Resolve() : Colossal.Mono.Cecil.PropertyDefinition`  

## Nested types

- `Colossal.Mono.Cecil.PropertyDefinition+<>c`  

