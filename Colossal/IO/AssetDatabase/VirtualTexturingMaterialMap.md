# Colossal.IO.AssetDatabase.VirtualTexturingMaterialMap

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `UnityEngine.ScriptableObject`  

## Code

```csharp
public class VirtualTexturingMaterialMap : UnityEngine.ScriptableObject
{
    public Colossal.IO.AssetDatabase.VTMaterialData[] materials;

    public VirtualTexturingMaterialMap();

    public Colossal.IO.AssetDatabase.VTMaterialData GetVTMaterialDataFromShader(UnityEngine.Shader shader);
    public Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription GetVTMaterialDescriptionFromShader(UnityEngine.Shader shader);
    public System.Boolean HasVTMaterialFor(UnityEngine.Shader shader);
}
```


## Fields

- `public Colossal.IO.AssetDatabase.VTMaterialData[] materials`  

```csharp
public Colossal.IO.AssetDatabase.VTMaterialData[] materials;
```


## Constructors

- `public VirtualTexturingMaterialMap()`  

```csharp
public VirtualTexturingMaterialMap();
```


## Methods

- `public GetVTMaterialDataFromShader(UnityEngine.Shader shader) : Colossal.IO.AssetDatabase.VTMaterialData`  

```csharp
public Colossal.IO.AssetDatabase.VTMaterialData GetVTMaterialDataFromShader(UnityEngine.Shader shader);
```

- `public GetVTMaterialDescriptionFromShader(UnityEngine.Shader shader) : Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription`  

```csharp
public Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription GetVTMaterialDescriptionFromShader(UnityEngine.Shader shader);
```

- `public HasVTMaterialFor(UnityEngine.Shader shader) : System.Boolean`  

```csharp
public System.Boolean HasVTMaterialFor(UnityEngine.Shader shader);
```


