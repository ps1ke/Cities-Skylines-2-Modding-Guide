# Colossal.IO.AssetDatabase.MaterialLibrary

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  

**Attributes:** `Serializable`  

## Fields

- `public System.Collections.Generic.List<Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription> m_Materials`  
- `private static Colossal.Logging.ILog log`  

## Constructors

- `public MaterialLibrary()`  

## Methods

- `public static CalculateHash(UnityEngine.Material material) : System.Int32`  
- `public Contains(System.Int32 hash) : System.Boolean`  
- `public GetMaterial(System.String name) : UnityEngine.Material`  
- `public GetMaterial(System.Int32 hash) : UnityEngine.Material`  
- `public GetMaterialDescription(System.Int32 hash) : Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription`  
- `public GetMaterialDescription(UnityEngine.Shader shader) : Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription`  
- `public GetMaterialHash(System.String name) : System.Int32`  
- `public GetMaterialHash(UnityEngine.Material material) : System.Int32`  
- `private OnEnable() : System.Void`  

## Nested types

- `Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription`  

