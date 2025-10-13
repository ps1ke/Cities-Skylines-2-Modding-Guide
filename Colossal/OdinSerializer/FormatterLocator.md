# Colossal.OdinSerializer.FormatterLocator

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class FormatterLocator
{
    private static readonly System.Object StrongFormatters_LOCK;
    private static readonly System.Object WeakFormatters_LOCK;
    private static readonly System.Collections.Generic.Dictionary<System.Type, Colossal.OdinSerializer.IFormatter> FormatterInstances;
    private static readonly Colossal.OdinSerializer.Utilities.DoubleLookupDictionary<System.Type, Colossal.OdinSerializer.ISerializationPolicy, Colossal.OdinSerializer.IFormatter> StrongTypeFormatterMap;
    private static readonly Colossal.OdinSerializer.Utilities.DoubleLookupDictionary<System.Type, Colossal.OdinSerializer.ISerializationPolicy, Colossal.OdinSerializer.IFormatter> WeakTypeFormatterMap;
    private static readonly System.Collections.Generic.List<Colossal.OdinSerializer.FormatterLocator+FormatterLocatorInfo> FormatterLocators;
    private static readonly System.Collections.Generic.List<Colossal.OdinSerializer.FormatterLocator+FormatterInfo> FormatterInfos;

    private static Colossal.OdinSerializer.IFormatter CreateFormatter(System.Type type, Colossal.OdinSerializer.ISerializationPolicy policy, System.Boolean allowWeakFormatters);
    internal static System.Collections.Generic.List<Colossal.OdinSerializer.IFormatter> GetAllCompatiblePredefinedFormatters(System.Type type, Colossal.OdinSerializer.ISerializationPolicy policy);
    private static System.Collections.Generic.IEnumerable<System.String> GetAllPossibleMissingAOTTypes(System.Type type);
    public static Colossal.OdinSerializer.IFormatter<T> GetFormatter<T>(Colossal.OdinSerializer.ISerializationPolicy policy);
    public static Colossal.OdinSerializer.IFormatter GetFormatter(System.Type type, Colossal.OdinSerializer.ISerializationPolicy policy);
    public static Colossal.OdinSerializer.IFormatter GetFormatter(System.Type type, Colossal.OdinSerializer.ISerializationPolicy policy, System.Boolean allowWeakFallbackFormatters);
    private static Colossal.OdinSerializer.IFormatter GetFormatterInstance(System.Type type);
    private static System.Void LogAOTError(System.Type type, System.Exception ex);
}
```


## Fields

- `private static readonly System.Object StrongFormatters_LOCK`  

```csharp
private static readonly System.Object StrongFormatters_LOCK;
```

- `private static readonly System.Object WeakFormatters_LOCK`  

```csharp
private static readonly System.Object WeakFormatters_LOCK;
```

- `private static readonly System.Collections.Generic.Dictionary<System.Type, Colossal.OdinSerializer.IFormatter> FormatterInstances`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.Type, Colossal.OdinSerializer.IFormatter> FormatterInstances;
```

- `private static readonly Colossal.OdinSerializer.Utilities.DoubleLookupDictionary<System.Type, Colossal.OdinSerializer.ISerializationPolicy, Colossal.OdinSerializer.IFormatter> StrongTypeFormatterMap`  

```csharp
private static readonly Colossal.OdinSerializer.Utilities.DoubleLookupDictionary<System.Type, Colossal.OdinSerializer.ISerializationPolicy, Colossal.OdinSerializer.IFormatter> StrongTypeFormatterMap;
```

- `private static readonly Colossal.OdinSerializer.Utilities.DoubleLookupDictionary<System.Type, Colossal.OdinSerializer.ISerializationPolicy, Colossal.OdinSerializer.IFormatter> WeakTypeFormatterMap`  

```csharp
private static readonly Colossal.OdinSerializer.Utilities.DoubleLookupDictionary<System.Type, Colossal.OdinSerializer.ISerializationPolicy, Colossal.OdinSerializer.IFormatter> WeakTypeFormatterMap;
```

- `private static readonly System.Collections.Generic.List<Colossal.OdinSerializer.FormatterLocator+FormatterLocatorInfo> FormatterLocators`  

```csharp
private static readonly System.Collections.Generic.List<Colossal.OdinSerializer.FormatterLocator+FormatterLocatorInfo> FormatterLocators;
```

- `private static readonly System.Collections.Generic.List<Colossal.OdinSerializer.FormatterLocator+FormatterInfo> FormatterInfos`  

```csharp
private static readonly System.Collections.Generic.List<Colossal.OdinSerializer.FormatterLocator+FormatterInfo> FormatterInfos;
```


## Methods

- `private static CreateFormatter(System.Type type, Colossal.OdinSerializer.ISerializationPolicy policy, System.Boolean allowWeakFormatters) : Colossal.OdinSerializer.IFormatter`  

```csharp
private static Colossal.OdinSerializer.IFormatter CreateFormatter(System.Type type, Colossal.OdinSerializer.ISerializationPolicy policy, System.Boolean allowWeakFormatters);
```

- `internal static GetAllCompatiblePredefinedFormatters(System.Type type, Colossal.OdinSerializer.ISerializationPolicy policy) : System.Collections.Generic.List<Colossal.OdinSerializer.IFormatter>`  

```csharp
internal static System.Collections.Generic.List<Colossal.OdinSerializer.IFormatter> GetAllCompatiblePredefinedFormatters(System.Type type, Colossal.OdinSerializer.ISerializationPolicy policy);
```

- `private static GetAllPossibleMissingAOTTypes(System.Type type) : System.Collections.Generic.IEnumerable<System.String>`  

```csharp
private static System.Collections.Generic.IEnumerable<System.String> GetAllPossibleMissingAOTTypes(System.Type type);
```

- `public static GetFormatter<T>(Colossal.OdinSerializer.ISerializationPolicy policy) : Colossal.OdinSerializer.IFormatter<T>`  

```csharp
public static Colossal.OdinSerializer.IFormatter<T> GetFormatter<T>(Colossal.OdinSerializer.ISerializationPolicy policy);
```

- `public static GetFormatter(System.Type type, Colossal.OdinSerializer.ISerializationPolicy policy) : Colossal.OdinSerializer.IFormatter`  

```csharp
public static Colossal.OdinSerializer.IFormatter GetFormatter(System.Type type, Colossal.OdinSerializer.ISerializationPolicy policy);
```

- `public static GetFormatter(System.Type type, Colossal.OdinSerializer.ISerializationPolicy policy, System.Boolean allowWeakFallbackFormatters) : Colossal.OdinSerializer.IFormatter`  

```csharp
public static Colossal.OdinSerializer.IFormatter GetFormatter(System.Type type, Colossal.OdinSerializer.ISerializationPolicy policy, System.Boolean allowWeakFallbackFormatters);
```

- `private static GetFormatterInstance(System.Type type) : Colossal.OdinSerializer.IFormatter`  

```csharp
private static Colossal.OdinSerializer.IFormatter GetFormatterInstance(System.Type type);
```

- `private static LogAOTError(System.Type type, System.Exception ex) : System.Void`  

```csharp
private static System.Void LogAOTError(System.Type type, System.Exception ex);
```


## Events

- `FormatterResolve` : `System.Func<System.Type, Colossal.OdinSerializer.IFormatter>`  

```csharp
public event System.Func<System.Type, Colossal.OdinSerializer.IFormatter> FormatterResolve;
```


## Nested types

- `Colossal.OdinSerializer.FormatterLocator+FormatterInfo`  
- `Colossal.OdinSerializer.FormatterLocator+FormatterLocatorInfo`  
- `Colossal.OdinSerializer.FormatterLocator+<>c`  
- `Colossal.OdinSerializer.FormatterLocator+<GetAllPossibleMissingAOTTypes>d__17`  

