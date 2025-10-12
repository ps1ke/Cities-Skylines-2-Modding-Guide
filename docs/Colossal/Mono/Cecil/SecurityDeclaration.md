# Colossal.Mono.Cecil.SecurityDeclaration

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `System.Object`  

## Fields

- `internal readonly System.UInt32 signature`  
- `private System.Byte[] blob`  
- `private readonly Colossal.Mono.Cecil.ModuleDefinition module`  
- `internal System.Boolean resolved`  
- `private Colossal.Mono.Cecil.SecurityAction action`  
- `internal Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.SecurityAttribute> security_attributes`  

## Properties

- `public Colossal.Mono.Cecil.SecurityAction Action { get; set }`  
- `public System.Boolean HasSecurityAttributes { get }`  
- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.SecurityAttribute> SecurityAttributes { get }`  
- `internal System.Boolean HasImage { internal get }`  

## Constructors

- `internal SecurityDeclaration(Colossal.Mono.Cecil.SecurityAction action, System.UInt32 signature, Colossal.Mono.Cecil.ModuleDefinition module)`  
- `public SecurityDeclaration(Colossal.Mono.Cecil.SecurityAction action)`  
- `public SecurityDeclaration(Colossal.Mono.Cecil.SecurityAction action, System.Byte[] blob)`  

## Methods

- `public GetBlob() : System.Byte[]`  
- `private Resolve() : System.Void`  

## Nested types

- `Colossal.Mono.Cecil.SecurityDeclaration+<>c`  

