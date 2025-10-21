# Game.Simulation.WaterSystem+QuadWaterBuffer

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct QuadWaterBuffer
{
    public UnityEngine.RenderTexture[] waterTextures;
    public UnityEngine.RenderTexture[] downdScaledFlowTextures;
    public UnityEngine.RenderTexture[] blurredFlowTextures;

    private UnityEngine.RenderTexture CreateRenderTexture(System.String name, Unity.Mathematics.int2 size, UnityEngine.Experimental.Rendering.GraphicsFormat format);
    public System.Void Dispose();
    public UnityEngine.RenderTexture FlowDownScaled(System.Int32 index);
    public System.Void Init(Unity.Mathematics.int2 size);
}
```


## Fields

- `public UnityEngine.RenderTexture[] waterTextures`  

```csharp
public UnityEngine.RenderTexture[] waterTextures;
```

- `public UnityEngine.RenderTexture[] downdScaledFlowTextures`  

```csharp
public UnityEngine.RenderTexture[] downdScaledFlowTextures;
```

- `public UnityEngine.RenderTexture[] blurredFlowTextures`  

```csharp
public UnityEngine.RenderTexture[] blurredFlowTextures;
```


## Methods

- `private CreateRenderTexture(System.String name, Unity.Mathematics.int2 size, UnityEngine.Experimental.Rendering.GraphicsFormat format) : UnityEngine.RenderTexture`  

```csharp
private UnityEngine.RenderTexture CreateRenderTexture(System.String name, Unity.Mathematics.int2 size, UnityEngine.Experimental.Rendering.GraphicsFormat format);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public FlowDownScaled(System.Int32 index) : UnityEngine.RenderTexture`  

```csharp
public UnityEngine.RenderTexture FlowDownScaled(System.Int32 index);
```

- `public Init(Unity.Mathematics.int2 size) : System.Void`  

```csharp
public System.Void Init(Unity.Mathematics.int2 size);
```


