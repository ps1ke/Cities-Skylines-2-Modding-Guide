# Colossal.AssetPipeline.Importers.Internal.ReaderExtensions

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers.Internal`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class ReaderExtensions
{
    private static T[] ReadArray<T>(System.IO.BinaryReader reader, System.Func<T> read);
    public static System.Int32[] ReadIntArray(System.IO.BinaryReader reader);
    public static T ReadObject<T>(System.IO.BinaryReader reader);
    public static T[] ReadObjectArray<T>(System.IO.BinaryReader reader);
    public static System.String[] ReadStringArray(System.IO.BinaryReader reader);
}
```


## Methods

- `private static ReadArray<T>(System.IO.BinaryReader reader, System.Func<T> read) : T[]`  

```csharp
private static T[] ReadArray<T>(System.IO.BinaryReader reader, System.Func<T> read);
```

- `public static ReadIntArray(System.IO.BinaryReader reader) : System.Int32[]`  

```csharp
public static System.Int32[] ReadIntArray(System.IO.BinaryReader reader);
```

- `public static ReadObject<T>(System.IO.BinaryReader reader) : T`  

```csharp
public static T ReadObject<T>(System.IO.BinaryReader reader);
```

- `public static ReadObjectArray<T>(System.IO.BinaryReader reader) : T[]`  

```csharp
public static T[] ReadObjectArray<T>(System.IO.BinaryReader reader);
```

- `public static ReadStringArray(System.IO.BinaryReader reader) : System.String[]`  

```csharp
public static System.String[] ReadStringArray(System.IO.BinaryReader reader);
```


## Nested types

- `Colossal.AssetPipeline.Importers.Internal.ReaderExtensions+<>c__DisplayClass0_0<T>`  
- `Colossal.AssetPipeline.Importers.Internal.ReaderExtensions+<>c__DisplayClass2_0`  
- `Colossal.AssetPipeline.Importers.Internal.ReaderExtensions+<>c__DisplayClass3_0`  

