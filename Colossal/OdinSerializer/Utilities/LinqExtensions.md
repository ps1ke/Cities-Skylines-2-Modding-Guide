# Colossal.OdinSerializer.Utilities.LinqExtensions

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer.Utilities`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class LinqExtensions
{
    public static System.Collections.Generic.IEnumerable<T> Append<T>(System.Collections.Generic.IEnumerable<T> source, System.Collections.Generic.IEnumerable<T> append);
    public static System.Collections.Generic.IEnumerable<T> ForEach<T>(System.Collections.Generic.IEnumerable<T> source, System.Action<T> action);
    public static System.Collections.Generic.IEnumerable<T> ForEach<T>(System.Collections.Generic.IEnumerable<T> source, System.Action<T, System.Int32> action);
}
```


## Methods

- `public static Append<T>(System.Collections.Generic.IEnumerable<T> source, System.Collections.Generic.IEnumerable<T> append) : System.Collections.Generic.IEnumerable<T>`  

```csharp
public static System.Collections.Generic.IEnumerable<T> Append<T>(System.Collections.Generic.IEnumerable<T> source, System.Collections.Generic.IEnumerable<T> append);
```

- `public static ForEach<T>(System.Collections.Generic.IEnumerable<T> source, System.Action<T> action) : System.Collections.Generic.IEnumerable<T>`  

```csharp
public static System.Collections.Generic.IEnumerable<T> ForEach<T>(System.Collections.Generic.IEnumerable<T> source, System.Action<T> action);
```

- `public static ForEach<T>(System.Collections.Generic.IEnumerable<T> source, System.Action<T, System.Int32> action) : System.Collections.Generic.IEnumerable<T>`  

```csharp
public static System.Collections.Generic.IEnumerable<T> ForEach<T>(System.Collections.Generic.IEnumerable<T> source, System.Action<T, System.Int32> action);
```


## Nested types

- `Colossal.OdinSerializer.Utilities.LinqExtensions+<Append>d__2<T>`  

