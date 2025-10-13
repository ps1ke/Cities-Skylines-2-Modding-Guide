# Colossal.UI.Binding.ValueWriters

**Assembly:** `Colossal.UI.Binding`  
**Namespace:** `Colossal.UI.Binding`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class ValueWriters
{
    private static readonly System.Collections.Generic.Dictionary<System.Type, System.Object> s_Writers;

    public static Colossal.UI.Binding.IWriter<T> Create<T>();
    public static System.Object Create(System.Type type);
    private static System.Type GetDictionaryInterface(System.Type type);
    private static System.Type GetListInterface(System.Type type);
    public static Colossal.UI.Binding.NullableWriter<T> Nullable<T>(Colossal.UI.Binding.IWriter<T> writer);
    public static System.Void Register<T>(Colossal.UI.Binding.WriterDelegate<T> func);
    public static System.Void Register<T>(Colossal.UI.Binding.IWriter<T> writer);
}
```


## Fields

- `private static readonly System.Collections.Generic.Dictionary<System.Type, System.Object> s_Writers`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.Type, System.Object> s_Writers;
```


## Methods

- `public static Create<T>() : Colossal.UI.Binding.IWriter<T>`  

```csharp
public static Colossal.UI.Binding.IWriter<T> Create<T>();
```

- `public static Create(System.Type type) : System.Object`  

```csharp
public static System.Object Create(System.Type type);
```

- `private static GetDictionaryInterface(System.Type type) : System.Type`  

```csharp
private static System.Type GetDictionaryInterface(System.Type type);
```

- `private static GetListInterface(System.Type type) : System.Type`  

```csharp
private static System.Type GetListInterface(System.Type type);
```

- `public static Nullable<T>(Colossal.UI.Binding.IWriter<T> writer) : Colossal.UI.Binding.NullableWriter<T>`  

```csharp
public static Colossal.UI.Binding.NullableWriter<T> Nullable<T>(Colossal.UI.Binding.IWriter<T> writer);
```

- `public static Register<T>(Colossal.UI.Binding.WriterDelegate<T> func) : System.Void`  

```csharp
public static System.Void Register<T>(Colossal.UI.Binding.WriterDelegate<T> func);
```

- `public static Register<T>(Colossal.UI.Binding.IWriter<T> writer) : System.Void`  

```csharp
public static System.Void Register<T>(Colossal.UI.Binding.IWriter<T> writer);
```


## Nested types

- `Colossal.UI.Binding.ValueWriters+<>c`  

