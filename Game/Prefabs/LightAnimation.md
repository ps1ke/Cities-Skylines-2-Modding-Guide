# Game.Prefabs.LightAnimation

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct LightAnimation : Unity.Entities.IBufferElementData
{
    public System.UInt32 m_DurationFrames;
    public Colossal.Collections.AnimationCurve1 m_AnimationCurve;
    public Game.Prefabs.SignalAnimation m_SignalAnimation;

}
```


## Fields

- `public System.UInt32 m_DurationFrames`  

```csharp
public System.UInt32 m_DurationFrames;
```

- `public Colossal.Collections.AnimationCurve1 m_AnimationCurve`  

```csharp
public Colossal.Collections.AnimationCurve1 m_AnimationCurve;
```

- `public Game.Prefabs.SignalAnimation m_SignalAnimation`  

```csharp
public Game.Prefabs.SignalAnimation m_SignalAnimation;
```


