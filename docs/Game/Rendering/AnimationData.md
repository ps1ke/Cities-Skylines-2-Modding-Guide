# Game.Rendering.AnimatedSystem+AnimationData

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct AnimationData
{
    private Unity.Collections.NativeQueue<Game.Rendering.AnimatedSystem+AnimationFrameData> m_AnimationFrameData;
    private Unity.Collections.NativeQueue<Game.Rendering.AnimatedSystem+ClipPriorityData> m_ClipPriorityData;

    public AnimationData(Unity.Collections.NativeQueue<Game.Rendering.AnimatedSystem+AnimationFrameData> animationFrameData, Unity.Collections.NativeQueue<Game.Rendering.AnimatedSystem+ClipPriorityData> clipPriorityData);

    private Game.Prefabs.AnimationClip GetClip(Unity.Entities.Entity style, Unity.Entities.DynamicBuffer<Game.Prefabs.AnimationClip> clips, System.Int32 index, System.Int32 priority);
    public System.Void SetAnimationFrame(Game.Prefabs.CharacterElement& characterElement, Unity.Entities.DynamicBuffer<Game.Prefabs.AnimationClip> clips, Game.Rendering.Animated& animated, Unity.Mathematics.float2 transition, System.Int32 priority, System.Boolean reset);
    private System.Void SetLayerData(Game.Rendering.AnimatedSystem+AnimationLayerData2& layerData, Game.Prefabs.AnimationClip& clipData0, Game.Prefabs.AnimationClip& clipData0I, Game.Prefabs.AnimationClip& clipData1, Game.Prefabs.AnimationClip& clipData1I, Unity.Mathematics.float2 time, Unity.Mathematics.float2 interpolation, System.Single transition);
    private System.Void SetLayerData(Game.Rendering.AnimatedSystem+AnimationLayerData& layerData, Game.Prefabs.AnimationClip& clipData0, Game.Prefabs.AnimationClip& clipData1, Unity.Mathematics.float2 time, System.Single transition);
    private System.Void SetLayerData(System.Int32& index, System.Single& frame, Game.Prefabs.AnimationClip& clipData, System.Single time);
}
```


## Fields

- `private Unity.Collections.NativeQueue<Game.Rendering.AnimatedSystem+AnimationFrameData> m_AnimationFrameData`  

```csharp
private Unity.Collections.NativeQueue<Game.Rendering.AnimatedSystem+AnimationFrameData> m_AnimationFrameData;
```

- `private Unity.Collections.NativeQueue<Game.Rendering.AnimatedSystem+ClipPriorityData> m_ClipPriorityData`  

```csharp
private Unity.Collections.NativeQueue<Game.Rendering.AnimatedSystem+ClipPriorityData> m_ClipPriorityData;
```


## Constructors

- `public AnimationData(Unity.Collections.NativeQueue<Game.Rendering.AnimatedSystem+AnimationFrameData> animationFrameData, Unity.Collections.NativeQueue<Game.Rendering.AnimatedSystem+ClipPriorityData> clipPriorityData)`  

```csharp
public AnimationData(Unity.Collections.NativeQueue<Game.Rendering.AnimatedSystem+AnimationFrameData> animationFrameData, Unity.Collections.NativeQueue<Game.Rendering.AnimatedSystem+ClipPriorityData> clipPriorityData);
```


## Methods

- `private GetClip(Unity.Entities.Entity style, Unity.Entities.DynamicBuffer<Game.Prefabs.AnimationClip> clips, System.Int32 index, System.Int32 priority) : Game.Prefabs.AnimationClip`  

```csharp
private Game.Prefabs.AnimationClip GetClip(Unity.Entities.Entity style, Unity.Entities.DynamicBuffer<Game.Prefabs.AnimationClip> clips, System.Int32 index, System.Int32 priority);
```

- `public SetAnimationFrame(Game.Prefabs.CharacterElement& characterElement, Unity.Entities.DynamicBuffer<Game.Prefabs.AnimationClip> clips, Game.Rendering.Animated& animated, Unity.Mathematics.float2 transition, System.Int32 priority, System.Boolean reset) : System.Void`  

```csharp
public System.Void SetAnimationFrame(Game.Prefabs.CharacterElement& characterElement, Unity.Entities.DynamicBuffer<Game.Prefabs.AnimationClip> clips, Game.Rendering.Animated& animated, Unity.Mathematics.float2 transition, System.Int32 priority, System.Boolean reset);
```

- `private SetLayerData(Game.Rendering.AnimatedSystem+AnimationLayerData2& layerData, Game.Prefabs.AnimationClip& clipData0, Game.Prefabs.AnimationClip& clipData0I, Game.Prefabs.AnimationClip& clipData1, Game.Prefabs.AnimationClip& clipData1I, Unity.Mathematics.float2 time, Unity.Mathematics.float2 interpolation, System.Single transition) : System.Void`  

```csharp
private System.Void SetLayerData(Game.Rendering.AnimatedSystem+AnimationLayerData2& layerData, Game.Prefabs.AnimationClip& clipData0, Game.Prefabs.AnimationClip& clipData0I, Game.Prefabs.AnimationClip& clipData1, Game.Prefabs.AnimationClip& clipData1I, Unity.Mathematics.float2 time, Unity.Mathematics.float2 interpolation, System.Single transition);
```

- `private SetLayerData(Game.Rendering.AnimatedSystem+AnimationLayerData& layerData, Game.Prefabs.AnimationClip& clipData0, Game.Prefabs.AnimationClip& clipData1, Unity.Mathematics.float2 time, System.Single transition) : System.Void`  

```csharp
private System.Void SetLayerData(Game.Rendering.AnimatedSystem+AnimationLayerData& layerData, Game.Prefabs.AnimationClip& clipData0, Game.Prefabs.AnimationClip& clipData1, Unity.Mathematics.float2 time, System.Single transition);
```

- `private SetLayerData(System.Int32& index, System.Single& frame, Game.Prefabs.AnimationClip& clipData, System.Single time) : System.Void`  

```csharp
private System.Void SetLayerData(System.Int32& index, System.Single& frame, Game.Prefabs.AnimationClip& clipData, System.Single time);
```


