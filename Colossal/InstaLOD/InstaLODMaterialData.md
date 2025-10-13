# Colossal.InstaLOD.InstaLODMaterialData

**Assembly:** `InstaLOD.Runtime`  
**Namespace:** `Colossal.InstaLOD`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct InstaLODMaterialData
{
    internal System.IntPtr m_Ptr;
    private System.IntPtr m_SDK;

    public System.Boolean isValid { get; }

    public InstaLODMaterialData(Colossal.InstaLOD.InstaLODSDK sdk);

    public Colossal.InstaLOD.InstaLODMaterial AddMaterial(System.Int32 id);
    public System.Void Dispose();
    public System.Void EnableOutput(System.String textureName, Colossal.InstaLOD.TextureType textureType);
    public System.Void SetDefaultColor(System.String textureName, UnityEngine.Color col);
    public System.Void SetOutputTextureSize(System.Int32 width, System.Int32 height);
}
```


## Fields

- `internal System.IntPtr m_Ptr`  

```csharp
internal System.IntPtr m_Ptr;
```

- `private System.IntPtr m_SDK`  

```csharp
private System.IntPtr m_SDK;
```


## Properties

- `public System.Boolean isValid { get }`  

```csharp
public System.Boolean isValid { get; }
```


## Constructors

- `public InstaLODMaterialData(Colossal.InstaLOD.InstaLODSDK sdk)`  

```csharp
public InstaLODMaterialData(Colossal.InstaLOD.InstaLODSDK sdk);
```


## Methods

- `public AddMaterial(System.Int32 id) : Colossal.InstaLOD.InstaLODMaterial`  

```csharp
public Colossal.InstaLOD.InstaLODMaterial AddMaterial(System.Int32 id);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public EnableOutput(System.String textureName, Colossal.InstaLOD.TextureType textureType) : System.Void`  

```csharp
public System.Void EnableOutput(System.String textureName, Colossal.InstaLOD.TextureType textureType);
```

- `public SetDefaultColor(System.String textureName, UnityEngine.Color col) : System.Void`  

```csharp
public System.Void SetDefaultColor(System.String textureName, UnityEngine.Color col);
```

- `public SetOutputTextureSize(System.Int32 width, System.Int32 height) : System.Void`  

```csharp
public System.Void SetOutputTextureSize(System.Int32 width, System.Int32 height);
```


