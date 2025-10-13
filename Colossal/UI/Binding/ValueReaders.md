# Colossal.UI.Binding.ValueReaders

**Assembly:** `Colossal.UI.Binding`  
**Namespace:** `Colossal.UI.Binding`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class ValueReaders
{
    private static readonly System.Collections.Generic.Dictionary<System.Type, System.Object> s_Readers;

    public static Colossal.UI.Binding.IReader<T> Create<T>();
    public static System.Object Create(System.Type type);
    private static System.Boolean IsDictionary(System.Type type);
    private static System.Boolean IsList(System.Type type);
    public static Colossal.UI.Binding.NullableReader<T> Nullable<T>(Colossal.UI.Binding.IReader<T> reader);
    public static System.Void Register<T>(Colossal.UI.Binding.ReaderDelegate<T> func);
    public static System.Void Register<T>(Colossal.UI.Binding.IReader<T> reader);
}
```


## Fields

- `private static readonly System.Collections.Generic.Dictionary<System.Type, System.Object> s_Readers`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.Type, System.Object> s_Readers;
```


## Methods

- `public static Create<T>() : Colossal.UI.Binding.IReader<T>`  

```csharp
public static Colossal.UI.Binding.IReader<T> Create<T>();
```

- `public static Create(System.Type type) : System.Object`  

```csharp
public static System.Object Create(System.Type type);
```

- `private static IsDictionary(System.Type type) : System.Boolean`  

```csharp
private static System.Boolean IsDictionary(System.Type type);
```

- `private static IsList(System.Type type) : System.Boolean`  

```csharp
private static System.Boolean IsList(System.Type type);
```

- `public static Nullable<T>(Colossal.UI.Binding.IReader<T> reader) : Colossal.UI.Binding.NullableReader<T>`  

```csharp
public static Colossal.UI.Binding.NullableReader<T> Nullable<T>(Colossal.UI.Binding.IReader<T> reader);
```

- `public static Register<T>(Colossal.UI.Binding.ReaderDelegate<T> func) : System.Void`  

```csharp
public static System.Void Register<T>(Colossal.UI.Binding.ReaderDelegate<T> func);
```

- `public static Register<T>(Colossal.UI.Binding.IReader<T> reader) : System.Void`  

```csharp
public static System.Void Register<T>(Colossal.UI.Binding.IReader<T> reader);
```


## Nested types

- `Colossal.UI.Binding.ValueReaders+<>c`  

