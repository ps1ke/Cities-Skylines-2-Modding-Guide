# Colossal.IO.AssetDatabase.MaterialLibrary

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  

**Attributes:** `Serializable`  

## Code

```csharp
public class MaterialLibrary
{
    public System.Collections.Generic.List<Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription> m_Materials;
    private static Colossal.Logging.ILog log;

    public MaterialLibrary();

    public static System.Int32 CalculateHash(UnityEngine.Material material);
    public System.Boolean Contains(System.Int32 hash);
    public UnityEngine.Material GetMaterial(System.String name);
    public UnityEngine.Material GetMaterial(System.Int32 hash);
    public Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription GetMaterialDescription(System.Int32 hash);
    public Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription GetMaterialDescription(UnityEngine.Shader shader);
    public System.Int32 GetMaterialHash(System.String name);
    public System.Int32 GetMaterialHash(UnityEngine.Material material);
    private System.Void OnEnable();
}
```


## Fields

- `public System.Collections.Generic.List<Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription> m_Materials`  

```csharp
public System.Collections.Generic.List<Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription> m_Materials;
```

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```


## Constructors

- `public MaterialLibrary()`  

```csharp
public MaterialLibrary();
```


## Methods

- `public static CalculateHash(UnityEngine.Material material) : System.Int32`  

```csharp
public static System.Int32 CalculateHash(UnityEngine.Material material);
```

- `public Contains(System.Int32 hash) : System.Boolean`  

```csharp
public System.Boolean Contains(System.Int32 hash);
```

- `public GetMaterial(System.String name) : UnityEngine.Material`  

```csharp
public UnityEngine.Material GetMaterial(System.String name);
```

- `public GetMaterial(System.Int32 hash) : UnityEngine.Material`  

```csharp
public UnityEngine.Material GetMaterial(System.Int32 hash);
```

- `public GetMaterialDescription(System.Int32 hash) : Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription`  

```csharp
public Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription GetMaterialDescription(System.Int32 hash);
```

- `public GetMaterialDescription(UnityEngine.Shader shader) : Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription`  

```csharp
public Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription GetMaterialDescription(UnityEngine.Shader shader);
```

- `public GetMaterialHash(System.String name) : System.Int32`  

```csharp
public System.Int32 GetMaterialHash(System.String name);
```

- `public GetMaterialHash(UnityEngine.Material material) : System.Int32`  

```csharp
public System.Int32 GetMaterialHash(UnityEngine.Material material);
```

- `private OnEnable() : System.Void`  

```csharp
private System.Void OnEnable();
```


## Nested types

- `Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription`  

