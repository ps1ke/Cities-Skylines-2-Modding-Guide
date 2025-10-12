# Colossal.Mono.Cecil.CustomAttribute

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.ICustomAttribute`  

**Attributes:** `DebuggerDisplay`  

## Fields

- `internal Colossal.Mono.Cecil.CustomAttributeValueProjection projection`  
- `internal readonly System.UInt32 signature`  
- `internal System.Boolean resolved`  
- `private Colossal.Mono.Cecil.MethodReference constructor`  
- `private System.Byte[] blob`  
- `internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeArgument> arguments`  
- `internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeNamedArgument> fields`  
- `internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeNamedArgument> properties`  

## Properties

- `public Colossal.Mono.Cecil.MethodReference Constructor { get; set }`  
- `public Colossal.Mono.Cecil.TypeReference AttributeType { get }`  
- `public System.Boolean IsResolved { get }`  
- `public System.Boolean HasConstructorArguments { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeArgument> ConstructorArguments { get }`  
- `public System.Boolean HasFields { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeNamedArgument> Fields { get }`  
- `public System.Boolean HasProperties { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttributeNamedArgument> Properties { get }`  
- `internal System.Boolean HasImage { internal get }`  
- `internal Colossal.Mono.Cecil.ModuleDefinition Module { internal get }`  

## Constructors

- `internal CustomAttribute(System.UInt32 signature, Colossal.Mono.Cecil.MethodReference constructor)`  
- `public CustomAttribute(Colossal.Mono.Cecil.MethodReference constructor)`  
- `public CustomAttribute(Colossal.Mono.Cecil.MethodReference constructor, System.Byte[] blob)`  

## Methods

- `private <Resolve>b__35_0(Colossal.Mono.Cecil.CustomAttribute attribute, Colossal.Mono.Cecil.MetadataReader reader) : System.Void`  
- `public GetBlob() : System.Byte[]`  
- `private Resolve() : System.Void`  

## Nested types

- `Colossal.Mono.Cecil.CustomAttribute+<>c`  

