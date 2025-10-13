# Colossal.OdinSerializer.FormatterEmitter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class FormatterEmitter
{
    private static System.Int32 helperFormatterNameId;
    public static const System.String PRE_EMITTED_ASSEMBLY_NAME;
    public static const System.String RUNTIME_EMITTED_ASSEMBLY_NAME;

    public static Colossal.OdinSerializer.IFormatter GetEmittedFormatter(System.Type type, Colossal.OdinSerializer.ISerializationPolicy policy);
}
```


## Fields

- `private static System.Int32 helperFormatterNameId`  

```csharp
private static System.Int32 helperFormatterNameId;
```

- `public static const System.String PRE_EMITTED_ASSEMBLY_NAME`  

```csharp
public static const System.String PRE_EMITTED_ASSEMBLY_NAME;
```

- `public static const System.String RUNTIME_EMITTED_ASSEMBLY_NAME`  

```csharp
public static const System.String RUNTIME_EMITTED_ASSEMBLY_NAME;
```


## Methods

- `public static GetEmittedFormatter(System.Type type, Colossal.OdinSerializer.ISerializationPolicy policy) : Colossal.OdinSerializer.IFormatter`  

```csharp
public static Colossal.OdinSerializer.IFormatter GetEmittedFormatter(System.Type type, Colossal.OdinSerializer.ISerializationPolicy policy);
```


## Nested types

- `Colossal.OdinSerializer.FormatterEmitter+AOTEmittedFormatter<T>`  
- `Colossal.OdinSerializer.FormatterEmitter+EmptyAOTEmittedFormatter<T>`  

