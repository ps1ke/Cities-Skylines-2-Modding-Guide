# Colossal.FileSystem.FileEntry

**Assembly:** `Colossal.IO`  
**Namespace:** `Colossal.FileSystem`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private System.String <path>k__BackingField`  
- `private System.Int64 <hash>k__BackingField`  
- `private System.Int32 <directory>k__BackingField`  

## Properties

- `public System.String path { get; private set }`  
- `public System.Int64 hash { get; private set }`  
- `public System.Int32 directory { get; private set }`  

## Constructors

- `public FileEntry(System.String file, System.Int32 dir)`  

## Methods

- `private CalculateHash() : System.Int64`  
- `public virtual Equals(System.Object obj) : System.Boolean`  
- `public virtual GetHashCode() : System.Int32`  
- `public SetHash(System.Int64 newHash) : System.Void`  
- `public virtual ToString() : System.String`  

