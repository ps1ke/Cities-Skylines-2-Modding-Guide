# Colossal.IO.AssetDatabase.BinaryWriterExtensions

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class BinaryWriterExtensions
{
    public static System.Void Write<T>(System.IO.BinaryWriter sw, System.Collections.Generic.Dictionary<System.String, T> dic);
    public static System.Void Write<T>(System.IO.BinaryWriter sw, T asset);
    public static System.Void Write(System.IO.BinaryWriter sw, Colossal.IO.AssetDatabase.AtlasFrame+Entry entry);
    public static System.Void Write(System.IO.BinaryWriter sw, System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.AtlasFrame+Entry> entries);
}
```


## Methods

- `public static Write<T>(System.IO.BinaryWriter sw, System.Collections.Generic.Dictionary<System.String, T> dic) : System.Void`  

```csharp
public static System.Void Write<T>(System.IO.BinaryWriter sw, System.Collections.Generic.Dictionary<System.String, T> dic);
```

- `public static Write<T>(System.IO.BinaryWriter sw, T asset) : System.Void`  

```csharp
public static System.Void Write<T>(System.IO.BinaryWriter sw, T asset);
```

- `public static Write(System.IO.BinaryWriter sw, Colossal.IO.AssetDatabase.AtlasFrame+Entry entry) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, Colossal.IO.AssetDatabase.AtlasFrame+Entry entry);
```

- `public static Write(System.IO.BinaryWriter sw, System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.AtlasFrame+Entry> entries) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.AtlasFrame+Entry> entries);
```


