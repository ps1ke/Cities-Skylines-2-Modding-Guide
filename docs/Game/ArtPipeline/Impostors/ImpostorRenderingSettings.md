# Game.ArtPipeline.Impostors.ImpostorRenderingSettings

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline.Impostors`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `Serializable`  

## Code

```csharp
public sealed struct ImpostorRenderingSettings
{
    public UnityEngine.Material Material;
    public System.Int32 AlphaTextureIndex;
    public System.Int32 DepthTextureIndex;
    public Game.ArtPipeline.Impostors.BakeMaterials+TextureBinding[] TextureBindings;

    public static Game.ArtPipeline.Impostors.ImpostorRenderingSettings Default { get; }

}
```


## Fields

- `public UnityEngine.Material Material`  

```csharp
public UnityEngine.Material Material;
```

- `public System.Int32 AlphaTextureIndex`  

```csharp
public System.Int32 AlphaTextureIndex;
```

- `public System.Int32 DepthTextureIndex`  

```csharp
public System.Int32 DepthTextureIndex;
```

- `public Game.ArtPipeline.Impostors.BakeMaterials+TextureBinding[] TextureBindings`  

```csharp
public Game.ArtPipeline.Impostors.BakeMaterials+TextureBinding[] TextureBindings;
```


## Properties

- `public static Game.ArtPipeline.Impostors.ImpostorRenderingSettings Default { get }`  

```csharp
public static Game.ArtPipeline.Impostors.ImpostorRenderingSettings Default { get; }
```


