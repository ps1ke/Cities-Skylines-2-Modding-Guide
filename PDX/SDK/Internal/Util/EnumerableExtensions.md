# PDX.SDK.Internal.Util.EnumerableExtensions

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Internal.Util`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class EnumerableExtensions
{
    public static System.Collections.Generic.IEnumerable<T> GetPage<T>(System.Linq.IOrderedEnumerable<T> valuesToPaginate, System.Int32 page, System.Int32 size);
    public static System.Collections.Generic.IEnumerable<T> GetPage<T>(System.Collections.Generic.IEnumerable<T> valuesToPaginate, System.Int32 page, System.Int32 size);
}
```


## Methods

- `public static GetPage<T>(System.Linq.IOrderedEnumerable<T> valuesToPaginate, System.Int32 page, System.Int32 size) : System.Collections.Generic.IEnumerable<T>`  

```csharp
public static System.Collections.Generic.IEnumerable<T> GetPage<T>(System.Linq.IOrderedEnumerable<T> valuesToPaginate, System.Int32 page, System.Int32 size);
```

- `public static GetPage<T>(System.Collections.Generic.IEnumerable<T> valuesToPaginate, System.Int32 page, System.Int32 size) : System.Collections.Generic.IEnumerable<T>`  

```csharp
public static System.Collections.Generic.IEnumerable<T> GetPage<T>(System.Collections.Generic.IEnumerable<T> valuesToPaginate, System.Int32 page, System.Int32 size);
```


