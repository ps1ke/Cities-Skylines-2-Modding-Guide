# Colossal.Mono.Cecil.GenericInstanceMethod

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.MethodSpecification`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`, `Colossal.Mono.Cecil.IMethodSignature`, `Colossal.Mono.Cecil.IGenericParameterProvider`, `Colossal.Mono.Cecil.IGenericContext`, `Colossal.Mono.Cecil.IGenericInstance`  

## Fields

- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.TypeReference> arguments`  

## Properties

- `public System.Boolean HasGenericArguments { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.TypeReference> GenericArguments { get }`  
- `public System.Boolean IsGenericInstance { get }`  
- `private Colossal.Mono.Cecil.IGenericParameterProvider Colossal.Mono.Cecil.IGenericContext.Method { private get }`  
- `private Colossal.Mono.Cecil.IGenericParameterProvider Colossal.Mono.Cecil.IGenericContext.Type { private get }`  
- `public System.Boolean ContainsGenericParameter { get }`  
- `public System.String FullName { get }`  

## Constructors

- `public GenericInstanceMethod(Colossal.Mono.Cecil.MethodReference method)`  
- `internal GenericInstanceMethod(Colossal.Mono.Cecil.MethodReference method, System.Int32 arity)`  

