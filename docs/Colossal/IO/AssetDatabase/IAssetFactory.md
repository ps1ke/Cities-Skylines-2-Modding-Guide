# Colossal.IO.AssetDatabase.IAssetFactory

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** interface abstract public  


## Methods

- `public abstract AddSupportedType<T>(System.String extension, System.Func<T> func, System.Boolean priorityExtension = False, System.Boolean isAddressable = True) : System.Void`  
- `public abstract AddSupportedType<T>(System.String[] extensions, System.Func<T> func, System.Boolean priorityExtension = False, System.Boolean isAddressable = True) : System.Void`  
- `public abstract AddSupportedType<T>(Colossal.IO.AssetDatabase.AddAssetFile createCallback, System.Boolean isAddressable = True) : System.Void`  
- `public abstract CreateAndRegisterAsset<T>(System.Type type, Colossal.IO.AssetDatabase.Identifier id, Colossal.IO.AssetDatabase.IAssetDatabase db) : T`  
- `public abstract GetAssetMimes<T>(System.Collections.Generic.IReadOnlyList`1[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& outMimes) : System.Boolean`  
- `public abstract GetAssetMimes(System.Type type, System.Collections.Generic.IReadOnlyList`1[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& outMimes) : System.Boolean`  
- `public abstract GetAssetType(System.String mime, System.Type& type) : System.Boolean`  
- `public abstract GetSupportedAssetTypes() : System.Collections.Generic.IReadOnlyCollection<System.Type>`  
- `public abstract GetSupportedExtensions() : System.Collections.Generic.IReadOnlyCollection<System.String>`  
- `public abstract GetSupportedExtensions(System.Boolean priorityData) : System.Collections.Generic.IReadOnlyCollection<System.String>`  
- `public abstract IsAddressable(System.Type type) : System.Boolean`  
- `public abstract IsAssignable(System.Type baseType, System.Type derivedType) : System.Boolean`  
- `public abstract MapSupportedExtension<T>(System.String extension, System.Boolean priorityExtension = False) : System.Void`  
- `public abstract MapSupportedExtension<T>(System.String[] extensions, System.Boolean priorityExtension = False) : System.Void`  
- `public abstract RemoveSupportedType<T>() : System.Void`  
- `public abstract UnmapSupportedExtension(System.String extension) : System.Void`  

