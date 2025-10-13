# Colossal.AssetPipeline.Surface

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`, `Colossal.AssetPipeline.ISurface`  

## Code

```csharp
public class Surface : System.IDisposable, Colossal.AssetPipeline.ISurface
{
    public readonly System.String name;
    public readonly System.Collections.Generic.Dictionary<System.String, Colossal.AssetPipeline.Importers.TextureImporter+Texture> bakingTextures;
    public readonly System.Collections.Generic.Dictionary<System.String, Colossal.AssetPipeline.Importers.TextureImporter+ITexture> textures;
    public readonly System.Collections.Generic.Dictionary<System.String, System.Single> floats;
    public readonly System.Collections.Generic.Dictionary<System.String, System.Int32> ints;
    public readonly System.Collections.Generic.Dictionary<System.String, UnityEngine.Vector4> vectors;
    public readonly System.Collections.Generic.Dictionary<System.String, UnityEngine.Color> colors;
    public readonly System.Collections.Generic.HashSet<System.String> keywords;
    public readonly System.Collections.Generic.List<Colossal.AssetPipeline.Surface+EmissiveLayer> emissiveLayers;
    private System.String m_Template;
    private UnityEngine.Material m_CachedObject;

    public System.String template { get; set; }
    public System.Boolean isValid { get; }
    public System.Boolean isImpostor { get; }

    public Surface(System.String name, System.String template);

    public System.Void AddBakingTexture(System.String name, Colossal.AssetPipeline.Importers.TextureImporter+Texture texture);
    public System.Void AddKeyword(System.String keyword);
    public System.Void AddProperty(System.String name, System.Single value);
    public System.Void AddProperty(System.String name, System.Int32 value);
    public System.Void AddProperty(System.String name, UnityEngine.Color value);
    public System.Void AddProperty(System.String name, UnityEngine.Vector4 value);
    public System.Void AddProperty(System.String name, Colossal.AssetPipeline.Importers.TextureImporter+ITexture texture);
    public System.Void Dispose();
    public Colossal.AssetPipeline.Importers.TextureImporter+Texture GetBakingTexture(System.String name);
    public UnityEngine.Color GetColorProperty(System.String name);
    public System.Single GetFloatProperty(System.String name);
    public virtual System.Int32 GetHashCode();
    public System.Int32 GetIntProperty(System.String name);
    public Colossal.AssetPipeline.Importers.TextureImporter+ITexture GetTextureProperty(System.String name);
    public T GetTextureProperty<T>(System.String name);
    public UnityEngine.Vector4 GetVectorProperty(System.String name);
    public System.Boolean HasAnyBakingTexture(System.String[] names);
    public System.Boolean HasAnyProperty(System.String[] names);
    public System.Boolean HasBakingTexture(System.String name);
    public System.Boolean HasProperty(System.String name);
    public System.Void RemoveBakingTexture(System.String name);
    public System.Void RemoveKeyword(System.String keyword);
    public System.Boolean RemoveProperty(System.String name);
    public UnityEngine.Material ToUnityMaterial(System.Boolean hideAndDontSave);
}
```


## Fields

- `public readonly System.String name`  

```csharp
public readonly System.String name;
```

- `public readonly System.Collections.Generic.Dictionary<System.String, Colossal.AssetPipeline.Importers.TextureImporter+Texture> bakingTextures`  

```csharp
public readonly System.Collections.Generic.Dictionary<System.String, Colossal.AssetPipeline.Importers.TextureImporter+Texture> bakingTextures;
```

- `public readonly System.Collections.Generic.Dictionary<System.String, Colossal.AssetPipeline.Importers.TextureImporter+ITexture> textures`  

```csharp
public readonly System.Collections.Generic.Dictionary<System.String, Colossal.AssetPipeline.Importers.TextureImporter+ITexture> textures;
```

- `public readonly System.Collections.Generic.Dictionary<System.String, System.Single> floats`  

```csharp
public readonly System.Collections.Generic.Dictionary<System.String, System.Single> floats;
```

- `public readonly System.Collections.Generic.Dictionary<System.String, System.Int32> ints`  

```csharp
public readonly System.Collections.Generic.Dictionary<System.String, System.Int32> ints;
```

- `public readonly System.Collections.Generic.Dictionary<System.String, UnityEngine.Vector4> vectors`  

```csharp
public readonly System.Collections.Generic.Dictionary<System.String, UnityEngine.Vector4> vectors;
```

- `public readonly System.Collections.Generic.Dictionary<System.String, UnityEngine.Color> colors`  

```csharp
public readonly System.Collections.Generic.Dictionary<System.String, UnityEngine.Color> colors;
```

- `public readonly System.Collections.Generic.HashSet<System.String> keywords`  

```csharp
public readonly System.Collections.Generic.HashSet<System.String> keywords;
```

- `public readonly System.Collections.Generic.List<Colossal.AssetPipeline.Surface+EmissiveLayer> emissiveLayers`  

```csharp
public readonly System.Collections.Generic.List<Colossal.AssetPipeline.Surface+EmissiveLayer> emissiveLayers;
```

- `private System.String m_Template`  

```csharp
private System.String m_Template;
```

- `private UnityEngine.Material m_CachedObject`  

```csharp
private UnityEngine.Material m_CachedObject;
```


## Properties

- `public System.String template { get; set }`  

```csharp
public System.String template { get; set; }
```

- `public System.Boolean isValid { get }`  

```csharp
public System.Boolean isValid { get; }
```

- `public System.Boolean isImpostor { get }`  

```csharp
public System.Boolean isImpostor { get; }
```


## Constructors

- `public Surface(System.String name, System.String template = null)`  

```csharp
public Surface(System.String name, System.String template);
```


## Methods

- `public AddBakingTexture(System.String name, Colossal.AssetPipeline.Importers.TextureImporter+Texture texture) : System.Void`  

```csharp
public System.Void AddBakingTexture(System.String name, Colossal.AssetPipeline.Importers.TextureImporter+Texture texture);
```

- `public AddKeyword(System.String keyword) : System.Void`  

```csharp
public System.Void AddKeyword(System.String keyword);
```

- `public AddProperty(System.String name, System.Single value) : System.Void`  

```csharp
public System.Void AddProperty(System.String name, System.Single value);
```

- `public AddProperty(System.String name, System.Int32 value) : System.Void`  

```csharp
public System.Void AddProperty(System.String name, System.Int32 value);
```

- `public AddProperty(System.String name, UnityEngine.Color value) : System.Void`  

```csharp
public System.Void AddProperty(System.String name, UnityEngine.Color value);
```

- `public AddProperty(System.String name, UnityEngine.Vector4 value) : System.Void`  

```csharp
public System.Void AddProperty(System.String name, UnityEngine.Vector4 value);
```

- `public AddProperty(System.String name, Colossal.AssetPipeline.Importers.TextureImporter+ITexture texture) : System.Void`  

```csharp
public System.Void AddProperty(System.String name, Colossal.AssetPipeline.Importers.TextureImporter+ITexture texture);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public GetBakingTexture(System.String name) : Colossal.AssetPipeline.Importers.TextureImporter+Texture`  

```csharp
public Colossal.AssetPipeline.Importers.TextureImporter+Texture GetBakingTexture(System.String name);
```

- `public GetColorProperty(System.String name) : UnityEngine.Color`  

```csharp
public UnityEngine.Color GetColorProperty(System.String name);
```

- `public GetFloatProperty(System.String name) : System.Single`  

```csharp
public System.Single GetFloatProperty(System.String name);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public GetIntProperty(System.String name) : System.Int32`  

```csharp
public System.Int32 GetIntProperty(System.String name);
```

- `public GetTextureProperty(System.String name) : Colossal.AssetPipeline.Importers.TextureImporter+ITexture`  

```csharp
public Colossal.AssetPipeline.Importers.TextureImporter+ITexture GetTextureProperty(System.String name);
```

- `public GetTextureProperty<T>(System.String name) : T`  

```csharp
public T GetTextureProperty<T>(System.String name);
```

- `public GetVectorProperty(System.String name) : UnityEngine.Vector4`  

```csharp
public UnityEngine.Vector4 GetVectorProperty(System.String name);
```

- `public HasAnyBakingTexture(System.String[] names) : System.Boolean`  

```csharp
public System.Boolean HasAnyBakingTexture(System.String[] names);
```

- `public HasAnyProperty(System.String[] names) : System.Boolean`  

```csharp
public System.Boolean HasAnyProperty(System.String[] names);
```

- `public HasBakingTexture(System.String name) : System.Boolean`  

```csharp
public System.Boolean HasBakingTexture(System.String name);
```

- `public HasProperty(System.String name) : System.Boolean`  

```csharp
public System.Boolean HasProperty(System.String name);
```

- `public RemoveBakingTexture(System.String name) : System.Void`  

```csharp
public System.Void RemoveBakingTexture(System.String name);
```

- `public RemoveKeyword(System.String keyword) : System.Void`  

```csharp
public System.Void RemoveKeyword(System.String keyword);
```

- `public RemoveProperty(System.String name) : System.Boolean`  

```csharp
public System.Boolean RemoveProperty(System.String name);
```

- `public ToUnityMaterial(System.Boolean hideAndDontSave = True) : UnityEngine.Material`  

```csharp
public UnityEngine.Material ToUnityMaterial(System.Boolean hideAndDontSave);
```


## Nested types

- `Colossal.AssetPipeline.Surface+EmissiveLayer`  

