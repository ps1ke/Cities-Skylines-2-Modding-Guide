# Colossal.Json.ProxyObject

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Json`  

**Type:** class sealed public  

**Base:** `Colossal.Json.Variant`  
**Implements:** `System.IConvertible`, `System.IEquatable<Colossal.Json.Variant>`, `System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, Colossal.Json.Variant>>`, `System.Collections.IEnumerable`  

**Attributes:** `DefaultMember`  

## Fields

- `private readonly System.Collections.Generic.Dictionary<System.String, Colossal.Json.Variant> dict`  
- `public static const System.String TypeHintKey`  

## Properties

- `public System.String TypeHint { get }`  
- `public Colossal.Json.Variant Item { get; set }`  
- `public System.Int32 Count { get }`  
- `public System.Collections.Generic.Dictionary<System.String, Colossal.Json.Variant> Keys { get }`  
- `public System.Collections.Generic.Dictionary<System.String, Colossal.Json.Variant> Values { get }`  

## Constructors

- `public ProxyObject()`  
- `public ProxyObject(System.Int32 capacity)`  

## Methods

- `public Add(System.String key, Colossal.Json.Variant item) : System.Void`  
- `public AddTypeHint(System.Type type) : System.Void`  
- `public ContainsKey(System.String key) : System.Boolean`  
- `public virtual Equals(Colossal.Json.Variant other) : System.Boolean`  
- `public Remove(System.String key) : System.Void`  
- `private System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String,Colossal.Json.Variant>>.GetEnumerator() : System.Collections.Generic.IEnumerator<System.Collections.Generic.KeyValuePair<System.String, Colossal.Json.Variant>>`  
- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  
- `public virtual TryGet(System.String key) : Colossal.Json.Variant`  
- `public virtual TryGetValue(System.String key, Colossal.Json.Variant& item) : System.Boolean`  

