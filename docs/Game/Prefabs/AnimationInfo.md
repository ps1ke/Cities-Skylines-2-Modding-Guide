# Game.Prefabs.CharacterStyle+AnimationInfo

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `System.Object`  

**Attributes:** `Serializable`  

## Code

```csharp
public class AnimationInfo
{
    public System.String name;
    public Colossal.IO.AssetDatabase.AssetReference<Colossal.IO.AssetDatabase.AnimationAsset> animationAsset;
    public Game.Prefabs.RenderPrefab target;
    public Colossal.Animations.AnimationType type;
    public Colossal.Animations.AnimationLayer layer;
    public System.Int32 frameCount;
    public System.Int32 frameRate;
    public System.Int32 rootMotionBone;
    public Game.Prefabs.CharacterStyle+AnimationMotion[] rootMotion;
    public Game.Prefabs.ActivityType activity;
    public Game.Prefabs.AnimationType state;
    public Game.Prefabs.ActivityCondition conditions;
    public Game.Prefabs.AnimationPlayback playback;

    public AnimationInfo();

}
```


## Fields

- `public System.String name`  

```csharp
public System.String name;
```

- `public Colossal.IO.AssetDatabase.AssetReference<Colossal.IO.AssetDatabase.AnimationAsset> animationAsset`  

```csharp
public Colossal.IO.AssetDatabase.AssetReference<Colossal.IO.AssetDatabase.AnimationAsset> animationAsset;
```

- `public Game.Prefabs.RenderPrefab target`  

```csharp
public Game.Prefabs.RenderPrefab target;
```

- `public Colossal.Animations.AnimationType type`  

```csharp
public Colossal.Animations.AnimationType type;
```

- `public Colossal.Animations.AnimationLayer layer`  

```csharp
public Colossal.Animations.AnimationLayer layer;
```

- `public System.Int32 frameCount`  

```csharp
public System.Int32 frameCount;
```

- `public System.Int32 frameRate`  

```csharp
public System.Int32 frameRate;
```

- `public System.Int32 rootMotionBone`  

```csharp
public System.Int32 rootMotionBone;
```

- `public Game.Prefabs.CharacterStyle+AnimationMotion[] rootMotion`  

```csharp
public Game.Prefabs.CharacterStyle+AnimationMotion[] rootMotion;
```

- `public Game.Prefabs.ActivityType activity`  

```csharp
public Game.Prefabs.ActivityType activity;
```

- `public Game.Prefabs.AnimationType state`  

```csharp
public Game.Prefabs.AnimationType state;
```

- `public Game.Prefabs.ActivityCondition conditions`  

```csharp
public Game.Prefabs.ActivityCondition conditions;
```

- `public Game.Prefabs.AnimationPlayback playback`  

```csharp
public Game.Prefabs.AnimationPlayback playback;
```


## Constructors

- `public AnimationInfo()`  

```csharp
public AnimationInfo();
```


