# Colossal.Mono.Cecil.GenericInstanceType

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.TypeSpecification`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`, `Colossal.Mono.Cecil.IGenericParameterProvider`, `Colossal.Mono.Cecil.IGenericContext`, `Colossal.Mono.Cecil.IGenericInstance`  

## Fields

- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.TypeReference> arguments`  

## Properties

- `public System.Boolean HasGenericArguments { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.TypeReference> GenericArguments { get }`  
- `public Colossal.Mono.Cecil.TypeReference DeclaringType { get; set }`  
- `public System.String FullName { get }`  
- `public System.Boolean IsGenericInstance { get }`  
- `public System.Boolean ContainsGenericParameter { get }`  
- `private Colossal.Mono.Cecil.IGenericParameterProvider Colossal.Mono.Cecil.IGenericContext.Type { private get }`  

## Constructors

- `public GenericInstanceType(Colossal.Mono.Cecil.TypeReference type)`  
- `internal GenericInstanceType(Colossal.Mono.Cecil.TypeReference type, System.Int32 arity)`  

