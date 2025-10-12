# Colossal.Mono.Cecil.AssemblyNameReference

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.IMetadataScope`, `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Fields

- `private System.String name`  
- `private System.String culture`  
- `private System.Version version`  
- `private System.UInt32 attributes`  
- `private System.Byte[] public_key`  
- `private System.Byte[] public_key_token`  
- `private Colossal.Mono.Cecil.AssemblyHashAlgorithm hash_algorithm`  
- `private System.Byte[] hash`  
- `internal Colossal.Mono.Cecil.MetadataToken token`  
- `private System.String full_name`  

## Properties

- `public System.String Name { get; set }`  
- `public System.String Culture { get; set }`  
- `public System.Version Version { get; set }`  
- `public Colossal.Mono.Cecil.AssemblyAttributes Attributes { get; set }`  
- `public System.Boolean HasPublicKey { get; set }`  
- `public System.Boolean IsSideBySideCompatible { get; set }`  
- `public System.Boolean IsRetargetable { get; set }`  
- `public System.Boolean IsWindowsRuntime { get; set }`  
- `public System.Byte[] PublicKey { get; set }`  
- `public System.Byte[] PublicKeyToken { get; set }`  
- `public Colossal.Mono.Cecil.MetadataScopeType MetadataScopeType { get }`  
- `public System.String FullName { get }`  
- `public Colossal.Mono.Cecil.AssemblyHashAlgorithm HashAlgorithm { get; set }`  
- `public System.Byte[] Hash { get; set }`  
- `public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set }`  

## Constructors

- `internal AssemblyNameReference()`  
- `public AssemblyNameReference(System.String name, System.Version version)`  

## Methods

- `private HashPublicKey() : System.Byte[]`  
- `public static Parse(System.String fullName) : Colossal.Mono.Cecil.AssemblyNameReference`  
- `public virtual ToString() : System.String`  

