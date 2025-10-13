# Colossal.IO.AssetDatabase.Internal.HelperExtensions

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.Internal`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class HelperExtensions
{
    public static System.Void Add<TKey, TValue>(System.Collections.Generic.Dictionary<TKey, TValue> dictionary, TKey[] keys, TValue value);
    public static System.Void ForEach<T>(System.Collections.Generic.IEnumerable<T> source, System.Action<T> action);
    public static System.Boolean TryGetValue<T, TV, TU>(System.Collections.Generic.Dictionary<T, TV> dict, T key, TU& value);
    public static System.Boolean TryGetValue<T, TV, TU>(System.Collections.Concurrent.ConcurrentDictionary<T, TV> dict, T key, TU& value);
}
```


## Methods

- `public static Add<TKey, TValue>(System.Collections.Generic.Dictionary<TKey, TValue> dictionary, TKey[] keys, TValue value) : System.Void`  

```csharp
public static System.Void Add<TKey, TValue>(System.Collections.Generic.Dictionary<TKey, TValue> dictionary, TKey[] keys, TValue value);
```

- `public static ForEach<T>(System.Collections.Generic.IEnumerable<T> source, System.Action<T> action) : System.Void`  

```csharp
public static System.Void ForEach<T>(System.Collections.Generic.IEnumerable<T> source, System.Action<T> action);
```

- `public static TryGetValue<T, TV, TU>(System.Collections.Generic.Dictionary<T, TV> dict, T key, TU& value) : System.Boolean`  

```csharp
public static System.Boolean TryGetValue<T, TV, TU>(System.Collections.Generic.Dictionary<T, TV> dict, T key, TU& value);
```

- `public static TryGetValue<T, TV, TU>(System.Collections.Concurrent.ConcurrentDictionary<T, TV> dict, T key, TU& value) : System.Boolean`  

```csharp
public static System.Boolean TryGetValue<T, TV, TU>(System.Collections.Concurrent.ConcurrentDictionary<T, TV> dict, T key, TU& value);
```


