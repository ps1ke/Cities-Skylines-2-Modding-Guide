# Colossal.Collections.Generic.BiDictionaryExtensions

**Assembly:** `Colossal.Collections`  
**Namespace:** `Colossal.Collections.Generic`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class BiDictionaryExtensions
{
    public static Colossal.Collections.Generic.BiDictionary<TKey, TValue> ToBiDictionary<TSource, TKey, TValue>(System.Collections.Generic.IEnumerable<TSource> source, System.Func<TSource, TKey> keySelector, System.Func<TSource, TValue> valueSelector);
}
```


## Methods

- `public static ToBiDictionary<TSource, TKey, TValue>(System.Collections.Generic.IEnumerable<TSource> source, System.Func<TSource, TKey> keySelector, System.Func<TSource, TValue> valueSelector) : Colossal.Collections.Generic.BiDictionary<TKey, TValue>`  

```csharp
public static Colossal.Collections.Generic.BiDictionary<TKey, TValue> ToBiDictionary<TSource, TKey, TValue>(System.Collections.Generic.IEnumerable<TSource> source, System.Func<TSource, TKey> keySelector, System.Func<TSource, TValue> valueSelector);
```


