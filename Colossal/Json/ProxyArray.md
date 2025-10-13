# Colossal.Json.ProxyArray

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Json`  

**Type:** class sealed public  

**Base:** `Colossal.Json.Variant`  
**Implements:** `System.IConvertible`, `System.IEquatable<Colossal.Json.Variant>`, `System.Collections.Generic.IEnumerable<Colossal.Json.Variant>`, `System.Collections.IEnumerable`  

**Attributes:** `DefaultMember`  

## Code

```csharp
public sealed class ProxyArray : Colossal.Json.Variant, System.IConvertible, System.IEquatable<Colossal.Json.Variant>, System.Collections.Generic.IEnumerable<Colossal.Json.Variant>, System.Collections.IEnumerable
{
    private readonly System.Collections.Generic.List<Colossal.Json.Variant> list;

    public Colossal.Json.Variant Item { get; set; }
    public System.Int32 Count { get; }

    public ProxyArray();
    public ProxyArray(System.Int32 capacity);

    public System.Void Add(Colossal.Json.Variant item);
    internal System.Boolean CanBeMultiRankArray(System.Int32[] rankLengths);
    private System.Boolean CanBeMultiRankArray(System.Int32 rank, System.Int32[] rankLengths);
    public virtual System.Boolean Equals(Colossal.Json.Variant other);
    private System.Collections.Generic.IEnumerator<Colossal.Json.Variant> System.Collections.Generic.IEnumerable<Colossal.Json.Variant>.GetEnumerator();
    private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
}
```


## Fields

- `private readonly System.Collections.Generic.List<Colossal.Json.Variant> list`  

```csharp
private readonly System.Collections.Generic.List<Colossal.Json.Variant> list;
```


## Properties

- `public Colossal.Json.Variant Item { get; set }`  

```csharp
public Colossal.Json.Variant Item { get; set; }
```

- `public System.Int32 Count { get }`  

```csharp
public System.Int32 Count { get; }
```


## Constructors

- `public ProxyArray()`  

```csharp
public ProxyArray();
```

- `public ProxyArray(System.Int32 capacity)`  

```csharp
public ProxyArray(System.Int32 capacity);
```


## Methods

- `public Add(Colossal.Json.Variant item) : System.Void`  

```csharp
public System.Void Add(Colossal.Json.Variant item);
```

- `internal CanBeMultiRankArray(System.Int32[] rankLengths) : System.Boolean`  

```csharp
internal System.Boolean CanBeMultiRankArray(System.Int32[] rankLengths);
```

- `private CanBeMultiRankArray(System.Int32 rank, System.Int32[] rankLengths) : System.Boolean`  

```csharp
private System.Boolean CanBeMultiRankArray(System.Int32 rank, System.Int32[] rankLengths);
```

- `public virtual Equals(Colossal.Json.Variant other) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(Colossal.Json.Variant other);
```

- `private System.Collections.Generic.IEnumerable<Colossal.Json.Variant>.GetEnumerator() : System.Collections.Generic.IEnumerator<Colossal.Json.Variant>`  

```csharp
private System.Collections.Generic.IEnumerator<Colossal.Json.Variant> System.Collections.Generic.IEnumerable<Colossal.Json.Variant>.GetEnumerator();
```

- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  

```csharp
private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
```


