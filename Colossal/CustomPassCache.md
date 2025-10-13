# Colossal.CustomPassCache

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class CustomPassCache
{
    private static System.Collections.Generic.Dictionary<System.String, UnityEngine.Rendering.HighDefinition.CustomPass> s_CachedPasses;

    private static System.Void ClearOnLoad();
    public static System.Boolean IsPassEnabled(System.String name, System.Boolean enabled);
    public static System.Boolean SetPassEnabled(System.String name, System.Boolean enabled);
}
```


## Fields

- `private static System.Collections.Generic.Dictionary<System.String, UnityEngine.Rendering.HighDefinition.CustomPass> s_CachedPasses`  

```csharp
private static System.Collections.Generic.Dictionary<System.String, UnityEngine.Rendering.HighDefinition.CustomPass> s_CachedPasses;
```


## Methods

- `private static ClearOnLoad() : System.Void`  

```csharp
private static System.Void ClearOnLoad();
```

- `public static IsPassEnabled(System.String name, System.Boolean enabled) : System.Boolean`  

```csharp
public static System.Boolean IsPassEnabled(System.String name, System.Boolean enabled);
```

- `public static SetPassEnabled(System.String name, System.Boolean enabled) : System.Boolean`  

```csharp
public static System.Boolean SetPassEnabled(System.String name, System.Boolean enabled);
```


## Nested types

- `Colossal.CustomPassCache+<>c`  

