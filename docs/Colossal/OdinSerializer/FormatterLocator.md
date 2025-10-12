# Colossal.OdinSerializer.FormatterLocator

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `private static readonly System.Object StrongFormatters_LOCK`  
- `private static readonly System.Object WeakFormatters_LOCK`  
- `private static readonly System.Collections.Generic.Dictionary<System.Type, Colossal.OdinSerializer.IFormatter> FormatterInstances`  
- `private static readonly Colossal.OdinSerializer.Utilities.DoubleLookupDictionary<System.Type, Colossal.OdinSerializer.ISerializationPolicy, Colossal.OdinSerializer.IFormatter> StrongTypeFormatterMap`  
- `private static readonly Colossal.OdinSerializer.Utilities.DoubleLookupDictionary<System.Type, Colossal.OdinSerializer.ISerializationPolicy, Colossal.OdinSerializer.IFormatter> WeakTypeFormatterMap`  
- `private static readonly System.Collections.Generic.List<Colossal.OdinSerializer.FormatterLocator+FormatterLocatorInfo> FormatterLocators`  
- `private static readonly System.Collections.Generic.List<Colossal.OdinSerializer.FormatterLocator+FormatterInfo> FormatterInfos`  

## Methods

- `private static CreateFormatter(System.Type type, Colossal.OdinSerializer.ISerializationPolicy policy, System.Boolean allowWeakFormatters) : Colossal.OdinSerializer.IFormatter`  
- `internal static GetAllCompatiblePredefinedFormatters(System.Type type, Colossal.OdinSerializer.ISerializationPolicy policy) : System.Collections.Generic.List<Colossal.OdinSerializer.IFormatter>`  
- `private static GetAllPossibleMissingAOTTypes(System.Type type) : System.Collections.Generic.IEnumerable<System.String>`  
- `public static GetFormatter<T>(Colossal.OdinSerializer.ISerializationPolicy policy) : Colossal.OdinSerializer.IFormatter<T>`  
- `public static GetFormatter(System.Type type, Colossal.OdinSerializer.ISerializationPolicy policy) : Colossal.OdinSerializer.IFormatter`  
- `public static GetFormatter(System.Type type, Colossal.OdinSerializer.ISerializationPolicy policy, System.Boolean allowWeakFallbackFormatters) : Colossal.OdinSerializer.IFormatter`  
- `private static GetFormatterInstance(System.Type type) : Colossal.OdinSerializer.IFormatter`  
- `private static LogAOTError(System.Type type, System.Exception ex) : System.Void`  

## Events

- `FormatterResolve` : `System.Func<System.Type, Colossal.OdinSerializer.IFormatter>`  

## Nested types

- `Colossal.OdinSerializer.FormatterLocator+FormatterInfo`  
- `Colossal.OdinSerializer.FormatterLocator+FormatterLocatorInfo`  
- `Colossal.OdinSerializer.FormatterLocator+<>c`  
- `Colossal.OdinSerializer.FormatterLocator+<GetAllPossibleMissingAOTTypes>d__17`  

