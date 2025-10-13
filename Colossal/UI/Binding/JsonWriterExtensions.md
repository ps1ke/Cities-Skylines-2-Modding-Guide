# Colossal.UI.Binding.JsonWriterExtensions

**Assembly:** `Colossal.UI.Binding`  
**Namespace:** `Colossal.UI.Binding`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class JsonWriterExtensions
{
    public static System.Void ArrayBegin(Colossal.UI.Binding.IJsonWriter writer, System.Int32 size);
    public static System.Void MapBegin(Colossal.UI.Binding.IJsonWriter writer, System.Int32 size);
    public static System.Void Write(Colossal.UI.Binding.IJsonWriter writer, System.String[] value);
    public static System.Void Write(Colossal.UI.Binding.IJsonWriter writer, System.Int32[] value);
    public static System.Void Write<T>(Colossal.UI.Binding.IJsonWriter writer, T value);
    public static System.Void Write<T>(Colossal.UI.Binding.IJsonWriter writer, System.Nullable<T> value);
    public static System.Void Write<T>(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.IList<T> value);
    public static System.Void Write(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.IList<System.String> value);
    public static System.Void Write(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.IReadOnlyDictionary<System.String, System.String> value);
    public static System.Void Write(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.IReadOnlyDictionary<System.String, System.Boolean> value);
    public static System.Void Write<T>(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.IReadOnlyDictionary<System.String, T> value);
    public static System.Void WriteEmptyArray(Colossal.UI.Binding.IJsonWriter writer);
    public static System.Void WriteEmptyMap(Colossal.UI.Binding.IJsonWriter writer);
    public static System.Void WriteNullable<T>(Colossal.UI.Binding.IJsonWriter writer, T value);
}
```


## Methods

- `public static ArrayBegin(Colossal.UI.Binding.IJsonWriter writer, System.Int32 size) : System.Void`  

```csharp
public static System.Void ArrayBegin(Colossal.UI.Binding.IJsonWriter writer, System.Int32 size);
```

- `public static MapBegin(Colossal.UI.Binding.IJsonWriter writer, System.Int32 size) : System.Void`  

```csharp
public static System.Void MapBegin(Colossal.UI.Binding.IJsonWriter writer, System.Int32 size);
```

- `public static Write(Colossal.UI.Binding.IJsonWriter writer, System.String[] value) : System.Void`  

```csharp
public static System.Void Write(Colossal.UI.Binding.IJsonWriter writer, System.String[] value);
```

- `public static Write(Colossal.UI.Binding.IJsonWriter writer, System.Int32[] value) : System.Void`  

```csharp
public static System.Void Write(Colossal.UI.Binding.IJsonWriter writer, System.Int32[] value);
```

- `public static Write<T>(Colossal.UI.Binding.IJsonWriter writer, T value) : System.Void`  

```csharp
public static System.Void Write<T>(Colossal.UI.Binding.IJsonWriter writer, T value);
```

- `public static Write<T>(Colossal.UI.Binding.IJsonWriter writer, System.Nullable<T> value) : System.Void`  

```csharp
public static System.Void Write<T>(Colossal.UI.Binding.IJsonWriter writer, System.Nullable<T> value);
```

- `public static Write<T>(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.IList<T> value) : System.Void`  

```csharp
public static System.Void Write<T>(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.IList<T> value);
```

- `public static Write(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.IList<System.String> value) : System.Void`  

```csharp
public static System.Void Write(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.IList<System.String> value);
```

- `public static Write(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.IReadOnlyDictionary<System.String, System.String> value) : System.Void`  

```csharp
public static System.Void Write(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.IReadOnlyDictionary<System.String, System.String> value);
```

- `public static Write(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.IReadOnlyDictionary<System.String, System.Boolean> value) : System.Void`  

```csharp
public static System.Void Write(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.IReadOnlyDictionary<System.String, System.Boolean> value);
```

- `public static Write<T>(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.IReadOnlyDictionary<System.String, T> value) : System.Void`  

```csharp
public static System.Void Write<T>(Colossal.UI.Binding.IJsonWriter writer, System.Collections.Generic.IReadOnlyDictionary<System.String, T> value);
```

- `public static WriteEmptyArray(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public static System.Void WriteEmptyArray(Colossal.UI.Binding.IJsonWriter writer);
```

- `public static WriteEmptyMap(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public static System.Void WriteEmptyMap(Colossal.UI.Binding.IJsonWriter writer);
```

- `public static WriteNullable<T>(Colossal.UI.Binding.IJsonWriter writer, T value) : System.Void`  

```csharp
public static System.Void WriteNullable<T>(Colossal.UI.Binding.IJsonWriter writer, T value);
```


