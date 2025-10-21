# Game.Rendering.Utilities.Extensions

**Assembly:** `Game`  
**Namespace:** `Game.Rendering.Utilities`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class Extensions
{
    public static System.Void Fire(System.Action action);
    public static System.Void Fire<T>(System.Action<T> action, T arg1);
    public static System.Void Fire<T, U>(System.Action<T, U> action, T arg1, U arg2);
}
```


## Methods

- `public static Fire(System.Action action) : System.Void`  

```csharp
public static System.Void Fire(System.Action action);
```

- `public static Fire<T>(System.Action<T> action, T arg1) : System.Void`  

```csharp
public static System.Void Fire<T>(System.Action<T> action, T arg1);
```

- `public static Fire<T, U>(System.Action<T, U> action, T arg1, U arg2) : System.Void`  

```csharp
public static System.Void Fire<T, U>(System.Action<T, U> action, T arg1, U arg2);
```


