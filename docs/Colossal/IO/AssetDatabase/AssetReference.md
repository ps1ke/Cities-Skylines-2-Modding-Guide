# Colossal.IO.AssetDatabase.AssetReference

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IComparable`, `System.IComparable<Colossal.Hash128>`, `System.IEquatable<Colossal.Hash128>`, `System.IEquatable<Colossal.IO.AssetDatabase.AssetReference>`  

**Attributes:** `Serializable`  

## Fields

- `private Colossal.Hash128 m_Guid`  
- `private System.Int32 m_GuidPart1`  
- `private System.Int32 m_GuidPart2`  
- `private System.Int32 m_GuidPart3`  
- `private System.Int32 m_GuidPart4`  

## Properties

- `public Colossal.Hash128 guid { get; set }`  

## Constructors

- `public AssetReference(Colossal.Hash128 guid)`  

## Methods

- `public CompareTo(System.Object obj) : System.Int32`  
- `public CompareTo(Colossal.Hash128 other) : System.Int32`  
- `public Equals(Colossal.Hash128 other) : System.Boolean`  
- `public Equals(Colossal.IO.AssetDatabase.AssetReference other) : System.Boolean`  
- `public virtual Equals(System.Object obj) : System.Boolean`  
- `public virtual GetHashCode() : System.Int32`  

