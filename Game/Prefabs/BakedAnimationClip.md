# Game.Prefabs.AnimationProperties+BakedAnimationClip

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `System.Object`  

**Attributes:** `Serializable`  

## Code

```csharp
public class BakedAnimationClip
{
    public System.String name;
    public System.Int32 pixelStart;
    public System.Int32 pixelEnd;
    public System.Single animationLength;
    public System.Boolean looping;
    public UnityEngine.Texture2DArray animationTexture;
    public Game.Prefabs.AnimationType m_Type;
    public Game.Prefabs.ActivityType m_Activity;
    public System.Single m_MovementSpeed;
    public Unity.Mathematics.float3 m_RootOffset;
    public Unity.Mathematics.quaternion m_RootRotation;

    public BakedAnimationClip(UnityEngine.Texture2DArray animTexture, Colossal.GPUAnimation.KeyframeTextureBaker+AnimationClipData clipData);

    public System.Void CalculatePlaybackData(Game.Prefabs.AnimationClip& clip);
}
```


## Fields

- `public System.String name`  

```csharp
public System.String name;
```

- `public System.Int32 pixelStart`  

```csharp
public System.Int32 pixelStart;
```

- `public System.Int32 pixelEnd`  

```csharp
public System.Int32 pixelEnd;
```

- `public System.Single animationLength`  

```csharp
public System.Single animationLength;
```

- `public System.Boolean looping`  

```csharp
public System.Boolean looping;
```

- `public UnityEngine.Texture2DArray animationTexture`  

```csharp
public UnityEngine.Texture2DArray animationTexture;
```

- `public Game.Prefabs.AnimationType m_Type`  

```csharp
public Game.Prefabs.AnimationType m_Type;
```

- `public Game.Prefabs.ActivityType m_Activity`  

```csharp
public Game.Prefabs.ActivityType m_Activity;
```

- `public System.Single m_MovementSpeed`  

```csharp
public System.Single m_MovementSpeed;
```

- `public Unity.Mathematics.float3 m_RootOffset`  

```csharp
public Unity.Mathematics.float3 m_RootOffset;
```

- `public Unity.Mathematics.quaternion m_RootRotation`  

```csharp
public Unity.Mathematics.quaternion m_RootRotation;
```


## Constructors

- `public BakedAnimationClip(UnityEngine.Texture2DArray animTexture, Colossal.GPUAnimation.KeyframeTextureBaker+AnimationClipData clipData)`  

```csharp
public BakedAnimationClip(UnityEngine.Texture2DArray animTexture, Colossal.GPUAnimation.KeyframeTextureBaker+AnimationClipData clipData);
```


## Methods

- `public CalculatePlaybackData(Game.Prefabs.AnimationClip& clip) : System.Void`  

```csharp
public System.Void CalculatePlaybackData(Game.Prefabs.AnimationClip& clip);
```


