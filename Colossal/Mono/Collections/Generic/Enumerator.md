# Colossal.Mono.Collections.Generic.Collection`1+Enumerator

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Collections.Generic`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.Collections.Generic.IEnumerator<T>`, `System.IDisposable`, `System.Collections.IEnumerator`  

## Code

```csharp
public sealed struct Enumerator<T> : System.Collections.Generic.IEnumerator<T>, System.IDisposable, System.Collections.IEnumerator
{
    private Colossal.Mono.Collections.Generic.Collection<T> collection;
    private T current;
    private System.Int32 next;
    private readonly System.Int32 version;

    public T Current { get; }
    private System.Object System.Collections.IEnumerator.Current { private get; }

    internal Enumerator(Colossal.Mono.Collections.Generic.Collection<T> collection);

    private System.Void CheckState();
    public System.Void Dispose();
    public System.Boolean MoveNext();
    public System.Void Reset();
}
```


## Fields

- `private Colossal.Mono.Collections.Generic.Collection<T> collection`  

```csharp
private Colossal.Mono.Collections.Generic.Collection<T> collection;
```

- `private T current`  

```csharp
private T current;
```

- `private System.Int32 next`  

```csharp
private System.Int32 next;
```

- `private readonly System.Int32 version`  

```csharp
private readonly System.Int32 version;
```


## Properties

- `public T Current { get }`  

```csharp
public T Current { get; }
```

- `private System.Object System.Collections.IEnumerator.Current { private get }`  

```csharp
private System.Object System.Collections.IEnumerator.Current { private get; }
```


## Constructors

- `internal Enumerator(Colossal.Mono.Collections.Generic.Collection<T> collection)`  

```csharp
internal Enumerator(Colossal.Mono.Collections.Generic.Collection<T> collection);
```


## Methods

- `private CheckState() : System.Void`  

```csharp
private System.Void CheckState();
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public MoveNext() : System.Boolean`  

```csharp
public System.Boolean MoveNext();
```

- `public Reset() : System.Void`  

```csharp
public System.Void Reset();
```


