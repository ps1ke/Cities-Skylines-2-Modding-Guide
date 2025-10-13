# Colossal.OdinSerializer.Utilities.ImmutableList

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer.Utilities`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.OdinSerializer.Utilities.IImmutableList<System.Object>`, `Colossal.OdinSerializer.Utilities.IImmutableList`, `System.Collections.IList`, `System.Collections.ICollection`, `System.Collections.IEnumerable`, `System.Collections.Generic.IList<System.Object>`, `System.Collections.Generic.ICollection<System.Object>`, `System.Collections.Generic.IEnumerable<System.Object>`  

**Attributes:** `DefaultMember`, `Serializable`  

## Code

```csharp
public sealed class ImmutableList : Colossal.OdinSerializer.Utilities.IImmutableList<System.Object>, Colossal.OdinSerializer.Utilities.IImmutableList, System.Collections.IList, System.Collections.ICollection, System.Collections.IEnumerable, System.Collections.Generic.IList<System.Object>, System.Collections.Generic.ICollection<System.Object>, System.Collections.Generic.IEnumerable<System.Object>
{
    private System.Collections.IList innerList;

    public System.Int32 Count { get; }
    public System.Boolean IsFixedSize { get; }
    public System.Boolean IsReadOnly { get; }
    public System.Boolean IsSynchronized { get; }
    public System.Object SyncRoot { get; }
    private System.Object System.Collections.IList.Item { private get; private set; }
    private System.Object System.Collections.Generic.IList<System.Object>.Item { private get; private set; }
    public System.Object Item { get; }

    public ImmutableList(System.Collections.IList innerList);

    public System.Boolean Contains(System.Object value);
    public System.Void CopyTo(System.Object[] array, System.Int32 arrayIndex);
    public System.Void CopyTo(System.Array array, System.Int32 index);
    public System.Collections.IEnumerator GetEnumerator();
    public System.Int32 IndexOf(System.Object value);
    private System.Void System.Collections.Generic.ICollection<System.Object>.Add(System.Object item);
    private System.Void System.Collections.Generic.ICollection<System.Object>.Clear();
    private System.Boolean System.Collections.Generic.ICollection<System.Object>.Remove(System.Object item);
    private System.Collections.Generic.IEnumerator<System.Object> System.Collections.Generic.IEnumerable<System.Object>.GetEnumerator();
    private System.Void System.Collections.Generic.IList<System.Object>.Insert(System.Int32 index, System.Object item);
    private System.Void System.Collections.Generic.IList<System.Object>.RemoveAt(System.Int32 index);
    private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
    private System.Int32 System.Collections.IList.Add(System.Object value);
    private System.Void System.Collections.IList.Clear();
    private System.Void System.Collections.IList.Insert(System.Int32 index, System.Object value);
    private System.Void System.Collections.IList.Remove(System.Object value);
    private System.Void System.Collections.IList.RemoveAt(System.Int32 index);
}
```


## Fields

- `private System.Collections.IList innerList`  

```csharp
private System.Collections.IList innerList;
```


## Properties

- `public System.Int32 Count { get }`  

```csharp
public System.Int32 Count { get; }
```

- `public System.Boolean IsFixedSize { get }`  

```csharp
public System.Boolean IsFixedSize { get; }
```

- `public System.Boolean IsReadOnly { get }`  

```csharp
public System.Boolean IsReadOnly { get; }
```

- `public System.Boolean IsSynchronized { get }`  

```csharp
public System.Boolean IsSynchronized { get; }
```

- `public System.Object SyncRoot { get }`  

```csharp
public System.Object SyncRoot { get; }
```

- `private System.Object System.Collections.IList.Item { private get; private set }`  

```csharp
private System.Object System.Collections.IList.Item { private get; private set; }
```

- `private System.Object System.Collections.Generic.IList<System.Object>.Item { private get; private set }`  

```csharp
private System.Object System.Collections.Generic.IList<System.Object>.Item { private get; private set; }
```

- `public System.Object Item { get }`  

```csharp
public System.Object Item { get; }
```


## Constructors

- `public ImmutableList(System.Collections.IList innerList)`  

```csharp
public ImmutableList(System.Collections.IList innerList);
```


## Methods

- `public Contains(System.Object value) : System.Boolean`  

```csharp
public System.Boolean Contains(System.Object value);
```

- `public CopyTo(System.Object[] array, System.Int32 arrayIndex) : System.Void`  

```csharp
public System.Void CopyTo(System.Object[] array, System.Int32 arrayIndex);
```

- `public CopyTo(System.Array array, System.Int32 index) : System.Void`  

```csharp
public System.Void CopyTo(System.Array array, System.Int32 index);
```

- `public GetEnumerator() : System.Collections.IEnumerator`  

```csharp
public System.Collections.IEnumerator GetEnumerator();
```

- `public IndexOf(System.Object value) : System.Int32`  

```csharp
public System.Int32 IndexOf(System.Object value);
```

- `private System.Collections.Generic.ICollection<System.Object>.Add(System.Object item) : System.Void`  

```csharp
private System.Void System.Collections.Generic.ICollection<System.Object>.Add(System.Object item);
```

- `private System.Collections.Generic.ICollection<System.Object>.Clear() : System.Void`  

```csharp
private System.Void System.Collections.Generic.ICollection<System.Object>.Clear();
```

- `private System.Collections.Generic.ICollection<System.Object>.Remove(System.Object item) : System.Boolean`  

```csharp
private System.Boolean System.Collections.Generic.ICollection<System.Object>.Remove(System.Object item);
```

- `private System.Collections.Generic.IEnumerable<System.Object>.GetEnumerator() : System.Collections.Generic.IEnumerator<System.Object>`  

```csharp
private System.Collections.Generic.IEnumerator<System.Object> System.Collections.Generic.IEnumerable<System.Object>.GetEnumerator();
```

- `private System.Collections.Generic.IList<System.Object>.Insert(System.Int32 index, System.Object item) : System.Void`  

```csharp
private System.Void System.Collections.Generic.IList<System.Object>.Insert(System.Int32 index, System.Object item);
```

- `private System.Collections.Generic.IList<System.Object>.RemoveAt(System.Int32 index) : System.Void`  

```csharp
private System.Void System.Collections.Generic.IList<System.Object>.RemoveAt(System.Int32 index);
```

- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  

```csharp
private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
```

- `private System.Collections.IList.Add(System.Object value) : System.Int32`  

```csharp
private System.Int32 System.Collections.IList.Add(System.Object value);
```

- `private System.Collections.IList.Clear() : System.Void`  

```csharp
private System.Void System.Collections.IList.Clear();
```

- `private System.Collections.IList.Insert(System.Int32 index, System.Object value) : System.Void`  

```csharp
private System.Void System.Collections.IList.Insert(System.Int32 index, System.Object value);
```

- `private System.Collections.IList.Remove(System.Object value) : System.Void`  

```csharp
private System.Void System.Collections.IList.Remove(System.Object value);
```

- `private System.Collections.IList.RemoveAt(System.Int32 index) : System.Void`  

```csharp
private System.Void System.Collections.IList.RemoveAt(System.Int32 index);
```


## Nested types

- `Colossal.OdinSerializer.Utilities.ImmutableList+<System-Collections-Generic-IEnumerable<System-Object>-GetEnumerator>d__25`  

