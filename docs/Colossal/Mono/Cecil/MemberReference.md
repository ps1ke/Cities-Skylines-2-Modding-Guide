# Colossal.Mono.Cecil.MemberReference

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Fields

- `private System.String name`  
- `private Colossal.Mono.Cecil.TypeReference declaring_type`  
- `internal Colossal.Mono.Cecil.MetadataToken token`  
- `internal System.Object projection`  

## Properties

- `public System.String Name { get; set }`  
- `public System.String FullName { get }`  
- `public Colossal.Mono.Cecil.TypeReference DeclaringType { get; set }`  
- `public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set }`  
- `public System.Boolean IsWindowsRuntimeProjection { get }`  
- `internal System.Boolean HasImage { internal get }`  
- `public Colossal.Mono.Cecil.ModuleDefinition Module { get }`  
- `public System.Boolean IsDefinition { get }`  
- `public System.Boolean ContainsGenericParameter { get }`  

## Constructors

- `internal MemberReference()`  
- `internal MemberReference(System.String name)`  

## Methods

- `internal MemberFullName() : System.String`  
- `public Resolve() : Colossal.Mono.Cecil.IMemberDefinition`  
- `protected abstract ResolveDefinition() : Colossal.Mono.Cecil.IMemberDefinition`  
- `public virtual ToString() : System.String`  

