# Colossal.Mono.Cecil.MetadataToken

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Colossal.Mono.Cecil.MetadataToken>`  

## Fields

- `private readonly System.UInt32 token`  
- `public static readonly Colossal.Mono.Cecil.MetadataToken Zero`  

## Properties

- `public System.UInt32 RID { get }`  
- `public Colossal.Mono.Cecil.TokenType TokenType { get }`  

## Constructors

- `public MetadataToken(System.UInt32 token)`  
- `public MetadataToken(Colossal.Mono.Cecil.TokenType type)`  
- `public MetadataToken(Colossal.Mono.Cecil.TokenType type, System.UInt32 rid)`  
- `public MetadataToken(Colossal.Mono.Cecil.TokenType type, System.Int32 rid)`  

## Methods

- `public Equals(Colossal.Mono.Cecil.MetadataToken other) : System.Boolean`  
- `public virtual Equals(System.Object obj) : System.Boolean`  
- `public virtual GetHashCode() : System.Int32`  
- `public ToInt32() : System.Int32`  
- `public virtual ToString() : System.String`  
- `public ToUInt32() : System.UInt32`  

