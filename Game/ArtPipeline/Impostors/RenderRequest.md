# Game.ArtPipeline.Impostors.RenderRequest

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline.Impostors`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct RenderRequest
{
    public System.Boolean isValid;
    public Game.ArtPipeline.Impostors.RenderRequestMode mode;
    public Game.ArtPipeline.Impostors.RenderRequestOutputSpace outputSpace;
    public UnityEngine.RenderTexture result;

    public RenderRequest(Game.ArtPipeline.Impostors.RenderRequestMode mode, UnityEngine.RenderTexture mask);

}
```


## Fields

- `public System.Boolean isValid`  

```csharp
public System.Boolean isValid;
```

- `public Game.ArtPipeline.Impostors.RenderRequestMode mode`  

```csharp
public Game.ArtPipeline.Impostors.RenderRequestMode mode;
```

- `public Game.ArtPipeline.Impostors.RenderRequestOutputSpace outputSpace`  

```csharp
public Game.ArtPipeline.Impostors.RenderRequestOutputSpace outputSpace;
```

- `public UnityEngine.RenderTexture result`  

```csharp
public UnityEngine.RenderTexture result;
```


## Constructors

- `public RenderRequest(Game.ArtPipeline.Impostors.RenderRequestMode mode, UnityEngine.RenderTexture mask)`  

```csharp
public RenderRequest(Game.ArtPipeline.Impostors.RenderRequestMode mode, UnityEngine.RenderTexture mask);
```


