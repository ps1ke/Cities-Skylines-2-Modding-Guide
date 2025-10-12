# Colossal.OdinSerializer.Utilities.ImmutableList

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer.Utilities`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.OdinSerializer.Utilities.IImmutableList<System.Object>`, `Colossal.OdinSerializer.Utilities.IImmutableList`, `System.Collections.IList`, `System.Collections.ICollection`, `System.Collections.IEnumerable`, `System.Collections.Generic.IList<System.Object>`, `System.Collections.Generic.ICollection<System.Object>`, `System.Collections.Generic.IEnumerable<System.Object>`  

**Attributes:** `DefaultMember`, `Serializable`  

## Fields

- `private System.Collections.IList innerList`  

## Properties

- `public System.Int32 Count { get }`  
- `public System.Boolean IsFixedSize { get }`  
- `public System.Boolean IsReadOnly { get }`  
- `public System.Boolean IsSynchronized { get }`  
- `public System.Object SyncRoot { get }`  
- `private System.Object System.Collections.IList.Item { private get; private set }`  
- `private System.Object System.Collections.Generic.IList<System.Object>.Item { private get; private set }`  
- `public System.Object Item { get }`  

## Constructors

- `public ImmutableList(System.Collections.IList innerList)`  

## Methods

- `public Contains(System.Object value) : System.Boolean`  
- `public CopyTo(System.Object[] array, System.Int32 arrayIndex) : System.Void`  
- `public CopyTo(System.Array array, System.Int32 index) : System.Void`  
- `public GetEnumerator() : System.Collections.IEnumerator`  
- `public IndexOf(System.Object value) : System.Int32`  
- `private System.Collections.Generic.ICollection<System.Object>.Add(System.Object item) : System.Void`  
- `private System.Collections.Generic.ICollection<System.Object>.Clear() : System.Void`  
- `private System.Collections.Generic.ICollection<System.Object>.Remove(System.Object item) : System.Boolean`  
- `private System.Collections.Generic.IEnumerable<System.Object>.GetEnumerator() : System.Collections.Generic.IEnumerator<System.Object>`  
- `private System.Collections.Generic.IList<System.Object>.Insert(System.Int32 index, System.Object item) : System.Void`  
- `private System.Collections.Generic.IList<System.Object>.RemoveAt(System.Int32 index) : System.Void`  
- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  
- `private System.Collections.IList.Add(System.Object value) : System.Int32`  
- `private System.Collections.IList.Clear() : System.Void`  
- `private System.Collections.IList.Insert(System.Int32 index, System.Object value) : System.Void`  
- `private System.Collections.IList.Remove(System.Object value) : System.Void`  
- `private System.Collections.IList.RemoveAt(System.Int32 index) : System.Void`  

## Nested types

- `Colossal.OdinSerializer.Utilities.ImmutableList+<System-Collections-Generic-IEnumerable<System-Object>-GetEnumerator>d__25`  

