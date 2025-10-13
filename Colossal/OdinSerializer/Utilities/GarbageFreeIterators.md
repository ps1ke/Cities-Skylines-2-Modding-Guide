# Colossal.OdinSerializer.Utilities.GarbageFreeIterators

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer.Utilities`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class GarbageFreeIterators
{
    public static Colossal.OdinSerializer.Utilities.GarbageFreeIterators+ListIterator<T> GFIterator<T>(System.Collections.Generic.List<T> list);
    public static Colossal.OdinSerializer.Utilities.GarbageFreeIterators+DictionaryIterator<T1, T2> GFIterator<T1, T2>(System.Collections.Generic.Dictionary<T1, T2> dictionary);
    public static Colossal.OdinSerializer.Utilities.GarbageFreeIterators+HashsetIterator<T> GFIterator<T>(System.Collections.Generic.HashSet<T> hashset);
    public static Colossal.OdinSerializer.Utilities.GarbageFreeIterators+DictionaryValueIterator<T1, T2> GFValueIterator<T1, T2>(System.Collections.Generic.Dictionary<T1, T2> dictionary);
}
```


## Methods

- `public static GFIterator<T>(System.Collections.Generic.List<T> list) : Colossal.OdinSerializer.Utilities.GarbageFreeIterators+ListIterator<T>`  

```csharp
public static Colossal.OdinSerializer.Utilities.GarbageFreeIterators+ListIterator<T> GFIterator<T>(System.Collections.Generic.List<T> list);
```

- `public static GFIterator<T1, T2>(System.Collections.Generic.Dictionary<T1, T2> dictionary) : Colossal.OdinSerializer.Utilities.GarbageFreeIterators+DictionaryIterator<T1, T2>`  

```csharp
public static Colossal.OdinSerializer.Utilities.GarbageFreeIterators+DictionaryIterator<T1, T2> GFIterator<T1, T2>(System.Collections.Generic.Dictionary<T1, T2> dictionary);
```

- `public static GFIterator<T>(System.Collections.Generic.HashSet<T> hashset) : Colossal.OdinSerializer.Utilities.GarbageFreeIterators+HashsetIterator<T>`  

```csharp
public static Colossal.OdinSerializer.Utilities.GarbageFreeIterators+HashsetIterator<T> GFIterator<T>(System.Collections.Generic.HashSet<T> hashset);
```

- `public static GFValueIterator<T1, T2>(System.Collections.Generic.Dictionary<T1, T2> dictionary) : Colossal.OdinSerializer.Utilities.GarbageFreeIterators+DictionaryValueIterator<T1, T2>`  

```csharp
public static Colossal.OdinSerializer.Utilities.GarbageFreeIterators+DictionaryValueIterator<T1, T2> GFValueIterator<T1, T2>(System.Collections.Generic.Dictionary<T1, T2> dictionary);
```


## Nested types

- `Colossal.OdinSerializer.Utilities.GarbageFreeIterators+ListIterator<T>`  
- `Colossal.OdinSerializer.Utilities.GarbageFreeIterators+HashsetIterator<T>`  
- `Colossal.OdinSerializer.Utilities.GarbageFreeIterators+DictionaryIterator<T1, T2>`  
- `Colossal.OdinSerializer.Utilities.GarbageFreeIterators+DictionaryValueIterator<T1, T2>`  

