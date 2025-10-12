# Colossal.IO.AssetDatabase.AsyncReadDescriptor

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Colossal.IO.AssetDatabase.AsyncReadDescriptor>`  

**Attributes:** `IsReadOnly`  

## Fields

- `public readonly System.String name`  
- `public readonly System.String path`  
- `public readonly System.Int64 offset`  
- `public readonly System.Int64 size`  
- `public readonly System.Boolean packaged`  

## Properties

- `public static Colossal.IO.AssetDatabase.AsyncReadDescriptor Invalid { get }`  

## Constructors

- `public AsyncReadDescriptor(System.String name, System.String path)`  
- `public AsyncReadDescriptor(System.String name, System.String path, System.Int64 offset, System.Int64 size, System.Boolean packaged)`  

## Methods

- `public Equals(Colossal.IO.AssetDatabase.AsyncReadDescriptor other) : System.Boolean`  
- `public virtual Equals(System.Object obj) : System.Boolean`  
- `public virtual GetHashCode() : System.Int32`  
- `public virtual ToString() : System.String`  

