# Game.Simulation.WaterSystem+QuadWaterBuffer

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `public UnityEngine.RenderTexture[] waterTextures`  
- `public UnityEngine.RenderTexture[] downdScaledFlowTextures`  
- `public UnityEngine.RenderTexture[] blurredFlowTextures`  

## Methods

- `private CreateRenderTexture(System.String name, Unity.Mathematics.int2 size, UnityEngine.Experimental.Rendering.GraphicsFormat format) : UnityEngine.RenderTexture`  
- `public Dispose() : System.Void`  
- `public FlowDownScaled(System.Int32 index) : UnityEngine.RenderTexture`  
- `public Init(Unity.Mathematics.int2 size) : System.Void`  

