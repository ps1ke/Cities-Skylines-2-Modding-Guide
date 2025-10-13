# Colossal.IO.AssetDatabase.IAssetFactory

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IAssetFactory
{
    public abstract System.Void AddSupportedType<T>(System.String extension, System.Func<T> func, System.Boolean priorityExtension, System.Boolean isAddressable);
    public abstract System.Void AddSupportedType<T>(System.String[] extensions, System.Func<T> func, System.Boolean priorityExtension, System.Boolean isAddressable);
    public abstract System.Void AddSupportedType<T>(Colossal.IO.AssetDatabase.AddAssetFile createCallback, System.Boolean isAddressable);
    public abstract T CreateAndRegisterAsset<T>(System.Type type, Colossal.IO.AssetDatabase.Identifier id, Colossal.IO.AssetDatabase.IAssetDatabase db);
    public abstract System.Boolean GetAssetMimes<T>(System.Collections.Generic.IReadOnlyList`1[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& outMimes);
    public abstract System.Boolean GetAssetMimes(System.Type type, System.Collections.Generic.IReadOnlyList`1[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& outMimes);
    public abstract System.Boolean GetAssetType(System.String mime, System.Type& type);
    public abstract System.Collections.Generic.IReadOnlyCollection<System.Type> GetSupportedAssetTypes();
    public abstract System.Collections.Generic.IReadOnlyCollection<System.String> GetSupportedExtensions();
    public abstract System.Collections.Generic.IReadOnlyCollection<System.String> GetSupportedExtensions(System.Boolean priorityData);
    public abstract System.Boolean IsAddressable(System.Type type);
    public abstract System.Boolean IsAssignable(System.Type baseType, System.Type derivedType);
    public abstract System.Void MapSupportedExtension<T>(System.String extension, System.Boolean priorityExtension);
    public abstract System.Void MapSupportedExtension<T>(System.String[] extensions, System.Boolean priorityExtension);
    public abstract System.Void RemoveSupportedType<T>();
    public abstract System.Void UnmapSupportedExtension(System.String extension);
}
```


## Methods

- `public abstract AddSupportedType<T>(System.String extension, System.Func<T> func, System.Boolean priorityExtension = False, System.Boolean isAddressable = True) : System.Void`  

```csharp
public abstract System.Void AddSupportedType<T>(System.String extension, System.Func<T> func, System.Boolean priorityExtension, System.Boolean isAddressable);
```

- `public abstract AddSupportedType<T>(System.String[] extensions, System.Func<T> func, System.Boolean priorityExtension = False, System.Boolean isAddressable = True) : System.Void`  

```csharp
public abstract System.Void AddSupportedType<T>(System.String[] extensions, System.Func<T> func, System.Boolean priorityExtension, System.Boolean isAddressable);
```

- `public abstract AddSupportedType<T>(Colossal.IO.AssetDatabase.AddAssetFile createCallback, System.Boolean isAddressable = True) : System.Void`  

```csharp
public abstract System.Void AddSupportedType<T>(Colossal.IO.AssetDatabase.AddAssetFile createCallback, System.Boolean isAddressable);
```

- `public abstract CreateAndRegisterAsset<T>(System.Type type, Colossal.IO.AssetDatabase.Identifier id, Colossal.IO.AssetDatabase.IAssetDatabase db) : T`  

```csharp
public abstract T CreateAndRegisterAsset<T>(System.Type type, Colossal.IO.AssetDatabase.Identifier id, Colossal.IO.AssetDatabase.IAssetDatabase db);
```

- `public abstract GetAssetMimes<T>(System.Collections.Generic.IReadOnlyList`1[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& outMimes) : System.Boolean`  

```csharp
public abstract System.Boolean GetAssetMimes<T>(System.Collections.Generic.IReadOnlyList`1[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& outMimes);
```

- `public abstract GetAssetMimes(System.Type type, System.Collections.Generic.IReadOnlyList`1[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& outMimes) : System.Boolean`  

```csharp
public abstract System.Boolean GetAssetMimes(System.Type type, System.Collections.Generic.IReadOnlyList`1[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& outMimes);
```

- `public abstract GetAssetType(System.String mime, System.Type& type) : System.Boolean`  

```csharp
public abstract System.Boolean GetAssetType(System.String mime, System.Type& type);
```

- `public abstract GetSupportedAssetTypes() : System.Collections.Generic.IReadOnlyCollection<System.Type>`  

```csharp
public abstract System.Collections.Generic.IReadOnlyCollection<System.Type> GetSupportedAssetTypes();
```

- `public abstract GetSupportedExtensions() : System.Collections.Generic.IReadOnlyCollection<System.String>`  

```csharp
public abstract System.Collections.Generic.IReadOnlyCollection<System.String> GetSupportedExtensions();
```

- `public abstract GetSupportedExtensions(System.Boolean priorityData) : System.Collections.Generic.IReadOnlyCollection<System.String>`  

```csharp
public abstract System.Collections.Generic.IReadOnlyCollection<System.String> GetSupportedExtensions(System.Boolean priorityData);
```

- `public abstract IsAddressable(System.Type type) : System.Boolean`  

```csharp
public abstract System.Boolean IsAddressable(System.Type type);
```

- `public abstract IsAssignable(System.Type baseType, System.Type derivedType) : System.Boolean`  

```csharp
public abstract System.Boolean IsAssignable(System.Type baseType, System.Type derivedType);
```

- `public abstract MapSupportedExtension<T>(System.String extension, System.Boolean priorityExtension = False) : System.Void`  

```csharp
public abstract System.Void MapSupportedExtension<T>(System.String extension, System.Boolean priorityExtension);
```

- `public abstract MapSupportedExtension<T>(System.String[] extensions, System.Boolean priorityExtension = False) : System.Void`  

```csharp
public abstract System.Void MapSupportedExtension<T>(System.String[] extensions, System.Boolean priorityExtension);
```

- `public abstract RemoveSupportedType<T>() : System.Void`  

```csharp
public abstract System.Void RemoveSupportedType<T>();
```

- `public abstract UnmapSupportedExtension(System.String extension) : System.Void`  

```csharp
public abstract System.Void UnmapSupportedExtension(System.String extension);
```


