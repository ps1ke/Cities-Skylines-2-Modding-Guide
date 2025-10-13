# Colossal.IO.AssetDatabase.BinaryReaderExtensions

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class BinaryReaderExtensions
{
    public static T ReadAssetData<T>(System.IO.BinaryReader sr);
    public static T ReadAssetData<T>(System.IO.BinaryReader sr, System.Boolean createDummy);
    public static System.Collections.Generic.List<Colossal.IO.AssetDatabase.AtlasFrame+Entry> ReadAtlasEntries(System.IO.BinaryReader sr);
    public static Colossal.IO.AssetDatabase.AtlasFrame+Entry ReadAtlasEntry(System.IO.BinaryReader sr);
    public static System.Collections.Generic.Dictionary<System.String, T> ReadStringAssetDataDictionary<T>(System.IO.BinaryReader sr);
    public static System.Collections.Generic.Dictionary<System.String, T> ReadStringAssetDataDictionary<T>(System.IO.BinaryReader sr, System.Boolean createDummies);
}
```


## Methods

- `public static ReadAssetData<T>(System.IO.BinaryReader sr) : T`  

```csharp
public static T ReadAssetData<T>(System.IO.BinaryReader sr);
```

- `public static ReadAssetData<T>(System.IO.BinaryReader sr, System.Boolean createDummy) : T`  

```csharp
public static T ReadAssetData<T>(System.IO.BinaryReader sr, System.Boolean createDummy);
```

- `public static ReadAtlasEntries(System.IO.BinaryReader sr) : System.Collections.Generic.List<Colossal.IO.AssetDatabase.AtlasFrame+Entry>`  

```csharp
public static System.Collections.Generic.List<Colossal.IO.AssetDatabase.AtlasFrame+Entry> ReadAtlasEntries(System.IO.BinaryReader sr);
```

- `public static ReadAtlasEntry(System.IO.BinaryReader sr) : Colossal.IO.AssetDatabase.AtlasFrame+Entry`  

```csharp
public static Colossal.IO.AssetDatabase.AtlasFrame+Entry ReadAtlasEntry(System.IO.BinaryReader sr);
```

- `public static ReadStringAssetDataDictionary<T>(System.IO.BinaryReader sr) : System.Collections.Generic.Dictionary<System.String, T>`  

```csharp
public static System.Collections.Generic.Dictionary<System.String, T> ReadStringAssetDataDictionary<T>(System.IO.BinaryReader sr);
```

- `public static ReadStringAssetDataDictionary<T>(System.IO.BinaryReader sr, System.Boolean createDummies) : System.Collections.Generic.Dictionary<System.String, T>`  

```csharp
public static System.Collections.Generic.Dictionary<System.String, T> ReadStringAssetDataDictionary<T>(System.IO.BinaryReader sr, System.Boolean createDummies);
```


