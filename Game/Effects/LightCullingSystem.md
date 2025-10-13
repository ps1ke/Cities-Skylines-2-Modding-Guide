# Game.Effects.LightCullingSystem

**Assembly:** `Game`  
**Namespace:** `Game.Effects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LightCullingSystem : Game.GameSystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Effects.EffectControlSystem m_EffectControlSystem;
    private Unity.Entities.EntityQuery m_LightEffectPrefabQuery;
    private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Effects.LightCullingSystem+LightEffectCullData> m_LightEffectCullData;
    private Unity.Collections.NativeQueue<Game.Effects.LightCullingSystem+VisibleLightData> m_VisibleLights;
    private Unity.Collections.NativeReference<System.Single> m_LastFrameMaxPunctualLightDistance;
    private Game.Effects.LightCullingSystem+TypeHandle __TypeHandle;
    private static Game.Effects.LightCullingSystem+DefaultLightParams s_DefaultLightParams;
    public static System.Boolean s_enableMinMaxLightCullingOptim;
    public static System.Single s_maxLightDistanceScale;
    public static System.Single s_minLightDistanceScale;

    public LightCullingSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void ComputeLightEffectCullData(Unity.Mathematics.float4 lodParameters);
    private static UnityEngine.Rendering.HighDefinition.GPULightType GetGPULightType(Game.Prefabs.Effects.LightEffect lightEffect);
    private System.Void GetRenderDataFromLigthEffet(UnityEngine.Rendering.HighDefinition.HDLightRenderData& hdLightRenderData, Game.Prefabs.LightEffectData lightEffectData, Game.Prefabs.Effects.LightEffect lightEffect, Unity.Mathematics.float4 lodParameters);
    private UnityEngine.Rendering.HighDefinition.AreaLightShape GetUnityAreaShape(Game.Rendering.AreaLightShape arealightShape);
    private UnityEngine.Rendering.HighDefinition.SpotLightShape GetUnitySpotShape(Game.Rendering.SpotLightShape spotlightShape);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    private System.Void ReadDefaultLightParams();
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.Effects.EffectControlSystem m_EffectControlSystem`  

```csharp
private Game.Effects.EffectControlSystem m_EffectControlSystem;
```

- `private Unity.Entities.EntityQuery m_LightEffectPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_LightEffectPrefabQuery;
```

- `private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Effects.LightCullingSystem+LightEffectCullData> m_LightEffectCullData`  

```csharp
private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Effects.LightCullingSystem+LightEffectCullData> m_LightEffectCullData;
```

- `private Unity.Collections.NativeQueue<Game.Effects.LightCullingSystem+VisibleLightData> m_VisibleLights`  

```csharp
private Unity.Collections.NativeQueue<Game.Effects.LightCullingSystem+VisibleLightData> m_VisibleLights;
```

- `private Unity.Collections.NativeReference<System.Single> m_LastFrameMaxPunctualLightDistance`  

```csharp
private Unity.Collections.NativeReference<System.Single> m_LastFrameMaxPunctualLightDistance;
```

- `private Game.Effects.LightCullingSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Effects.LightCullingSystem+TypeHandle __TypeHandle;
```

- `private static Game.Effects.LightCullingSystem+DefaultLightParams s_DefaultLightParams`  

```csharp
private static Game.Effects.LightCullingSystem+DefaultLightParams s_DefaultLightParams;
```

- `public static System.Boolean s_enableMinMaxLightCullingOptim`  

```csharp
public static System.Boolean s_enableMinMaxLightCullingOptim;
```

- `public static System.Single s_maxLightDistanceScale`  

```csharp
public static System.Single s_maxLightDistanceScale;
```

- `public static System.Single s_minLightDistanceScale`  

```csharp
public static System.Single s_minLightDistanceScale;
```


## Constructors

- `public LightCullingSystem()`  

```csharp
public LightCullingSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private ComputeLightEffectCullData(Unity.Mathematics.float4 lodParameters) : System.Void`  

```csharp
private System.Void ComputeLightEffectCullData(Unity.Mathematics.float4 lodParameters);
```

- `private static GetGPULightType(Game.Prefabs.Effects.LightEffect lightEffect) : UnityEngine.Rendering.HighDefinition.GPULightType`  

```csharp
private static UnityEngine.Rendering.HighDefinition.GPULightType GetGPULightType(Game.Prefabs.Effects.LightEffect lightEffect);
```

- `private GetRenderDataFromLigthEffet(UnityEngine.Rendering.HighDefinition.HDLightRenderData& hdLightRenderData, Game.Prefabs.LightEffectData lightEffectData, Game.Prefabs.Effects.LightEffect lightEffect, Unity.Mathematics.float4 lodParameters) : System.Void`  

```csharp
private System.Void GetRenderDataFromLigthEffet(UnityEngine.Rendering.HighDefinition.HDLightRenderData& hdLightRenderData, Game.Prefabs.LightEffectData lightEffectData, Game.Prefabs.Effects.LightEffect lightEffect, Unity.Mathematics.float4 lodParameters);
```

- `private GetUnityAreaShape(Game.Rendering.AreaLightShape arealightShape) : UnityEngine.Rendering.HighDefinition.AreaLightShape`  

```csharp
private UnityEngine.Rendering.HighDefinition.AreaLightShape GetUnityAreaShape(Game.Rendering.AreaLightShape arealightShape);
```

- `private GetUnitySpotShape(Game.Rendering.SpotLightShape spotlightShape) : UnityEngine.Rendering.HighDefinition.SpotLightShape`  

```csharp
private UnityEngine.Rendering.HighDefinition.SpotLightShape GetUnitySpotShape(Game.Rendering.SpotLightShape spotlightShape);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private ReadDefaultLightParams() : System.Void`  

```csharp
private System.Void ReadDefaultLightParams();
```


## Nested types

- `Game.Effects.LightCullingSystem+DefaultLightParams`  
- `Game.Effects.LightCullingSystem+LightEffectCullData`  
- `Game.Effects.LightCullingSystem+LightCullingJob`  
- `Game.Effects.LightCullingSystem+VisibleLightData`  
- `Game.Effects.LightCullingSystem+SortAndBuildPunctualLightsJob`  
- `Game.Effects.LightCullingSystem+TypeHandle`  

