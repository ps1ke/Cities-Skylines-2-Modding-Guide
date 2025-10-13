# Colossal.IO.AssetDatabase.Converter

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.Json.IJsonConverter<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.Json.IJsonConverter`  

## Code

```csharp
public class Converter : Colossal.Json.IJsonConverter<Colossal.IO.AssetDatabase.IAssetData>, Colossal.Json.IJsonConverter
{
    public Converter();

    public Colossal.IO.AssetDatabase.IAssetData FromJson(Colossal.Json.Variant variant);
    public Colossal.Json.Variant ToJson(Colossal.IO.AssetDatabase.IAssetData value);
}
```


## Constructors

- `public Converter()`  

```csharp
public Converter();
```


## Methods

- `public FromJson(Colossal.Json.Variant variant) : Colossal.IO.AssetDatabase.IAssetData`  

```csharp
public Colossal.IO.AssetDatabase.IAssetData FromJson(Colossal.Json.Variant variant);
```

- `public ToJson(Colossal.IO.AssetDatabase.IAssetData value) : Colossal.Json.Variant`  

```csharp
public Colossal.Json.Variant ToJson(Colossal.IO.AssetDatabase.IAssetData value);
```


