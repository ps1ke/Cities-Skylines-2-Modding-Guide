# Colossal.Mono.Collections.Generic.Collection`1+Enumerator

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Collections.Generic`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.Collections.Generic.IEnumerator<T>`, `System.IDisposable`, `System.Collections.IEnumerator`  

## Fields

- `private Colossal.Mono.Collections.Generic.Collection<T> collection`  
- `private T current`  
- `private System.Int32 next`  
- `private readonly System.Int32 version`  

## Properties

- `public T Current { get }`  
- `private System.Object System.Collections.IEnumerator.Current { private get }`  

## Constructors

- `internal Enumerator(Colossal.Mono.Collections.Generic.Collection<T> collection)`  

## Methods

- `private CheckState() : System.Void`  
- `public Dispose() : System.Void`  
- `public MoveNext() : System.Boolean`  
- `public Reset() : System.Void`  

