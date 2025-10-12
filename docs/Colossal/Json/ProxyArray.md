# Colossal.Json.ProxyArray

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Json`  

**Type:** class sealed public  

**Base:** `Colossal.Json.Variant`  
**Implements:** `System.IConvertible`, `System.IEquatable<Colossal.Json.Variant>`, `System.Collections.Generic.IEnumerable<Colossal.Json.Variant>`, `System.Collections.IEnumerable`  

**Attributes:** `DefaultMember`  

## Fields

- `private readonly System.Collections.Generic.List<Colossal.Json.Variant> list`  

## Properties

- `public Colossal.Json.Variant Item { get; set }`  
- `public System.Int32 Count { get }`  

## Constructors

- `public ProxyArray()`  
- `public ProxyArray(System.Int32 capacity)`  

## Methods

- `public Add(Colossal.Json.Variant item) : System.Void`  
- `internal CanBeMultiRankArray(System.Int32[] rankLengths) : System.Boolean`  
- `private CanBeMultiRankArray(System.Int32 rank, System.Int32[] rankLengths) : System.Boolean`  
- `public virtual Equals(Colossal.Json.Variant other) : System.Boolean`  
- `private System.Collections.Generic.IEnumerable<Colossal.Json.Variant>.GetEnumerator() : System.Collections.Generic.IEnumerator<Colossal.Json.Variant>`  
- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  

