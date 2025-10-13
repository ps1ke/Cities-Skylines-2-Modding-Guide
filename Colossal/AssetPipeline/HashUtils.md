# Colossal.AssetPipeline.HashUtils

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class HashUtils
{
    public static Colossal.Hash128 CreateNew();
    public static Colossal.Hash128 GetHash(Colossal.AssetPipeline.LOD lod, System.String rootPath);
    public static Colossal.Hash128 GetHash(Colossal.Animations.AnimationClip animation, System.String rootPath);
    public static Colossal.Hash128 GetHash(Colossal.AssetPipeline.Surface surface, System.String rootPath);
    public static Colossal.Hash128 GetHash(Colossal.Animations.Animation animation, System.String rootPath);
    public static Colossal.Hash128 GetHash(Colossal.AssetPipeline.Importers.TextureImporter+ITexture texture, System.String rootPath);
    public static Colossal.Hash128 GetHash(UnityEngine.Texture texture, System.String rootPath);
    private static System.Void GetRandomHash(Colossal.Hash128& hash);
}
```


## Methods

- `public static CreateNew() : Colossal.Hash128`  

```csharp
public static Colossal.Hash128 CreateNew();
```

- `public static GetHash(Colossal.AssetPipeline.LOD lod, System.String rootPath) : Colossal.Hash128`  

```csharp
public static Colossal.Hash128 GetHash(Colossal.AssetPipeline.LOD lod, System.String rootPath);
```

- `public static GetHash(Colossal.Animations.AnimationClip animation, System.String rootPath) : Colossal.Hash128`  

```csharp
public static Colossal.Hash128 GetHash(Colossal.Animations.AnimationClip animation, System.String rootPath);
```

- `public static GetHash(Colossal.AssetPipeline.Surface surface, System.String rootPath) : Colossal.Hash128`  

```csharp
public static Colossal.Hash128 GetHash(Colossal.AssetPipeline.Surface surface, System.String rootPath);
```

- `public static GetHash(Colossal.Animations.Animation animation, System.String rootPath) : Colossal.Hash128`  

```csharp
public static Colossal.Hash128 GetHash(Colossal.Animations.Animation animation, System.String rootPath);
```

- `public static GetHash(Colossal.AssetPipeline.Importers.TextureImporter+ITexture texture, System.String rootPath) : Colossal.Hash128`  

```csharp
public static Colossal.Hash128 GetHash(Colossal.AssetPipeline.Importers.TextureImporter+ITexture texture, System.String rootPath);
```

- `public static GetHash(UnityEngine.Texture texture, System.String rootPath) : Colossal.Hash128`  

```csharp
public static Colossal.Hash128 GetHash(UnityEngine.Texture texture, System.String rootPath);
```

- `private static GetRandomHash(Colossal.Hash128& hash) : System.Void`  

```csharp
private static System.Void GetRandomHash(Colossal.Hash128& hash);
```


