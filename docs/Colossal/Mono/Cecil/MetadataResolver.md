# Colossal.Mono.Cecil.MetadataResolver

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.IMetadataResolver`  

## Fields

- `private readonly Colossal.Mono.Cecil.IAssemblyResolver assembly_resolver`  

## Properties

- `public Colossal.Mono.Cecil.IAssemblyResolver AssemblyResolver { get }`  

## Constructors

- `public MetadataResolver(Colossal.Mono.Cecil.IAssemblyResolver assemblyResolver)`  

## Methods

- `private static AreSame(Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ParameterDefinition> a, Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ParameterDefinition> b) : System.Boolean`  
- `private static AreSame(Colossal.Mono.Cecil.TypeSpecification a, Colossal.Mono.Cecil.TypeSpecification b) : System.Boolean`  
- `private static AreSame(Colossal.Mono.Cecil.ArrayType a, Colossal.Mono.Cecil.ArrayType b) : System.Boolean`  
- `private static AreSame(Colossal.Mono.Cecil.IModifierType a, Colossal.Mono.Cecil.IModifierType b) : System.Boolean`  
- `private static AreSame(Colossal.Mono.Cecil.GenericInstanceType a, Colossal.Mono.Cecil.GenericInstanceType b) : System.Boolean`  
- `private static AreSame(Colossal.Mono.Cecil.GenericParameter a, Colossal.Mono.Cecil.GenericParameter b) : System.Boolean`  
- `private static AreSame(Colossal.Mono.Cecil.TypeReference a, Colossal.Mono.Cecil.TypeReference b) : System.Boolean`  
- `private GetField(Colossal.Mono.Cecil.TypeDefinition type, Colossal.Mono.Cecil.FieldReference reference) : Colossal.Mono.Cecil.FieldDefinition`  
- `private static GetField(Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.FieldDefinition> fields, Colossal.Mono.Cecil.FieldReference reference) : Colossal.Mono.Cecil.FieldDefinition`  
- `private GetMethod(Colossal.Mono.Cecil.TypeDefinition type, Colossal.Mono.Cecil.MethodReference reference) : Colossal.Mono.Cecil.MethodDefinition`  
- `public static GetMethod(Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodDefinition> methods, Colossal.Mono.Cecil.MethodReference reference) : Colossal.Mono.Cecil.MethodDefinition`  
- `private static GetType(Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.Cecil.TypeReference reference) : Colossal.Mono.Cecil.TypeDefinition`  
- `private static GetTypeDefinition(Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.Cecil.TypeReference type) : Colossal.Mono.Cecil.TypeDefinition`  
- `private static IsVarArgCallTo(Colossal.Mono.Cecil.MethodDefinition method, Colossal.Mono.Cecil.MethodReference reference) : System.Boolean`  
- `public virtual Resolve(Colossal.Mono.Cecil.TypeReference type) : Colossal.Mono.Cecil.TypeDefinition`  
- `public virtual Resolve(Colossal.Mono.Cecil.FieldReference field) : Colossal.Mono.Cecil.FieldDefinition`  
- `public virtual Resolve(Colossal.Mono.Cecil.MethodReference method) : Colossal.Mono.Cecil.MethodDefinition`  

