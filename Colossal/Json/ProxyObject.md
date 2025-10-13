# Colossal.Json.ProxyObject

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Json`  

**Type:** class sealed public  

**Base:** `Colossal.Json.Variant`  
**Implements:** `System.IConvertible`, `System.IEquatable<Colossal.Json.Variant>`, `System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, Colossal.Json.Variant>>`, `System.Collections.IEnumerable`  

**Attributes:** `DefaultMember`  

## Code

```csharp
public sealed class ProxyObject : Colossal.Json.Variant, System.IConvertible, System.IEquatable<Colossal.Json.Variant>, System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, Colossal.Json.Variant>>, System.Collections.IEnumerable
{
    private readonly System.Collections.Generic.Dictionary<System.String, Colossal.Json.Variant> dict;
    public static const System.String TypeHintKey;

    public System.String TypeHint { get; }
    public Colossal.Json.Variant Item { get; set; }
    public System.Int32 Count { get; }
    public System.Collections.Generic.Dictionary<System.String, Colossal.Json.Variant> Keys { get; }
    public System.Collections.Generic.Dictionary<System.String, Colossal.Json.Variant> Values { get; }

    public ProxyObject();
    public ProxyObject(System.Int32 capacity);

    public System.Void Add(System.String key, Colossal.Json.Variant item);
    public System.Void AddTypeHint(System.Type type);
    public System.Boolean ContainsKey(System.String key);
    public virtual System.Boolean Equals(Colossal.Json.Variant other);
    public System.Void Remove(System.String key);
    private System.Collections.Generic.IEnumerator<System.Collections.Generic.KeyValuePair<System.String, Colossal.Json.Variant>> System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String,Colossal.Json.Variant>>.GetEnumerator();
    private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
    public virtual Colossal.Json.Variant TryGet(System.String key);
    public virtual System.Boolean TryGetValue(System.String key, Colossal.Json.Variant& item);
}
```


## Fields

- `private readonly System.Collections.Generic.Dictionary<System.String, Colossal.Json.Variant> dict`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.String, Colossal.Json.Variant> dict;
```

- `public static const System.String TypeHintKey`  

```csharp
public static const System.String TypeHintKey;
```


## Properties

- `public System.String TypeHint { get }`  

```csharp
public System.String TypeHint { get; }
```

- `public Colossal.Json.Variant Item { get; set }`  

```csharp
public Colossal.Json.Variant Item { get; set; }
```

- `public System.Int32 Count { get }`  

```csharp
public System.Int32 Count { get; }
```

- `public System.Collections.Generic.Dictionary<System.String, Colossal.Json.Variant> Keys { get }`  

```csharp
public System.Collections.Generic.Dictionary<System.String, Colossal.Json.Variant> Keys { get; }
```

- `public System.Collections.Generic.Dictionary<System.String, Colossal.Json.Variant> Values { get }`  

```csharp
public System.Collections.Generic.Dictionary<System.String, Colossal.Json.Variant> Values { get; }
```


## Constructors

- `public ProxyObject()`  

```csharp
public ProxyObject();
```

- `public ProxyObject(System.Int32 capacity)`  

```csharp
public ProxyObject(System.Int32 capacity);
```


## Methods

- `public Add(System.String key, Colossal.Json.Variant item) : System.Void`  

```csharp
public System.Void Add(System.String key, Colossal.Json.Variant item);
```

- `public AddTypeHint(System.Type type) : System.Void`  

```csharp
public System.Void AddTypeHint(System.Type type);
```

- `public ContainsKey(System.String key) : System.Boolean`  

```csharp
public System.Boolean ContainsKey(System.String key);
```

- `public virtual Equals(Colossal.Json.Variant other) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(Colossal.Json.Variant other);
```

- `public Remove(System.String key) : System.Void`  

```csharp
public System.Void Remove(System.String key);
```

- `private System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String,Colossal.Json.Variant>>.GetEnumerator() : System.Collections.Generic.IEnumerator<System.Collections.Generic.KeyValuePair<System.String, Colossal.Json.Variant>>`  

```csharp
private System.Collections.Generic.IEnumerator<System.Collections.Generic.KeyValuePair<System.String, Colossal.Json.Variant>> System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String,Colossal.Json.Variant>>.GetEnumerator();
```

- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  

```csharp
private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
```

- `public virtual TryGet(System.String key) : Colossal.Json.Variant`  

```csharp
public virtual Colossal.Json.Variant TryGet(System.String key);
```

- `public virtual TryGetValue(System.String key, Colossal.Json.Variant& item) : System.Boolean`  

```csharp
public virtual System.Boolean TryGetValue(System.String key, Colossal.Json.Variant& item);
```


