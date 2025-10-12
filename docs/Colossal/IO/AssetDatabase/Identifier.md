# Colossal.IO.AssetDatabase.Identifier

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Colossal.IO.AssetDatabase.Identifier>`, `System.IComparable<Colossal.IO.AssetDatabase.Identifier>`  

## Fields

- `public readonly Colossal.Hash128 guid`  
- `public System.String uri`  
- `public static Colossal.IO.AssetDatabase.Identifier None`  

## Constructors

- `public Identifier(Colossal.Hash128 guid)`  
- `public Identifier(Colossal.Hash128 guid, System.String uri)`  

## Methods

- `public CompareTo(Colossal.IO.AssetDatabase.Identifier other) : System.Int32`  
- `public Equals(Colossal.IO.AssetDatabase.Identifier other) : System.Boolean`  
- `public virtual Equals(System.Object obj) : System.Boolean`  
- `public virtual GetHashCode() : System.Int32`  
- `internal ReplaceUri(System.String uri) : System.Void`  
- `public virtual ToString() : System.String`  

