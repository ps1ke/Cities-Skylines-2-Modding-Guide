# Colossal.OdinSerializer.Utilities.UnityVersion

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer.Utilities`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class UnityVersion
{
    public static readonly System.Int32 Major;
    public static readonly System.Int32 Minor;

    private static System.Void EnsureLoaded();
    public static System.Boolean IsVersionOrGreater(System.Int32 major, System.Int32 minor);
}
```


## Fields

- `public static readonly System.Int32 Major`  

```csharp
public static readonly System.Int32 Major;
```

- `public static readonly System.Int32 Minor`  

```csharp
public static readonly System.Int32 Minor;
```


## Methods

- `private static EnsureLoaded() : System.Void`  

```csharp
private static System.Void EnsureLoaded();
```

- `public static IsVersionOrGreater(System.Int32 major, System.Int32 minor) : System.Boolean`  

```csharp
public static System.Boolean IsVersionOrGreater(System.Int32 major, System.Int32 minor);
```


