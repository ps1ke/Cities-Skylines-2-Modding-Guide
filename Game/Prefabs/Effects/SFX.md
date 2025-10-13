# Game.Prefabs.Effects.SFX

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Effects`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class SFX : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public UnityEngine.AudioClip m_AudioClip;
    public System.Single m_Volume;
    public System.Single m_Pitch;
    public System.Single m_SpatialBlend;
    public System.Single m_Doppler;
    public System.Single m_Spread;
    public UnityEngine.AudioRolloffMode m_RolloffMode;
    public Unity.Mathematics.float2 m_MinMaxDistance;
    public System.Boolean m_Loop;
    public Game.Effects.MixerGroup m_MixerGroup;
    public System.Byte m_Priority;
    public UnityEngine.AnimationCurve m_RolloffCurve;
    public Unity.Mathematics.float3 m_SourceSize;
    public Unity.Mathematics.float2 m_FadeTimes;
    public System.Boolean m_RandomStartTime;

    public SFX();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public UnityEngine.AudioClip m_AudioClip`  

```csharp
public UnityEngine.AudioClip m_AudioClip;
```

- `public System.Single m_Volume`  

```csharp
public System.Single m_Volume;
```

- `public System.Single m_Pitch`  

```csharp
public System.Single m_Pitch;
```

- `public System.Single m_SpatialBlend`  

```csharp
public System.Single m_SpatialBlend;
```

- `public System.Single m_Doppler`  

```csharp
public System.Single m_Doppler;
```

- `public System.Single m_Spread`  

```csharp
public System.Single m_Spread;
```

- `public UnityEngine.AudioRolloffMode m_RolloffMode`  

```csharp
public UnityEngine.AudioRolloffMode m_RolloffMode;
```

- `public Unity.Mathematics.float2 m_MinMaxDistance`  

```csharp
public Unity.Mathematics.float2 m_MinMaxDistance;
```

- `public System.Boolean m_Loop`  

```csharp
public System.Boolean m_Loop;
```

- `public Game.Effects.MixerGroup m_MixerGroup`  

```csharp
public Game.Effects.MixerGroup m_MixerGroup;
```

- `public System.Byte m_Priority`  

```csharp
public System.Byte m_Priority;
```

- `public UnityEngine.AnimationCurve m_RolloffCurve`  

```csharp
public UnityEngine.AnimationCurve m_RolloffCurve;
```

- `public Unity.Mathematics.float3 m_SourceSize`  

```csharp
public Unity.Mathematics.float3 m_SourceSize;
```

- `public Unity.Mathematics.float2 m_FadeTimes`  

```csharp
public Unity.Mathematics.float2 m_FadeTimes;
```

- `public System.Boolean m_RandomStartTime`  

```csharp
public System.Boolean m_RandomStartTime;
```


## Constructors

- `public SFX()`  

```csharp
public SFX();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


