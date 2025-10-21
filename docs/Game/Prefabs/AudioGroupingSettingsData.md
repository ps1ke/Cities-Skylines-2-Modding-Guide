# Game.Prefabs.AudioGroupingSettingsData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

## Code

```csharp
public sealed struct AudioGroupingSettingsData : Unity.Entities.IBufferElementData
{
    public Game.Simulation.GroupAmbienceType m_Type;
    public Unity.Mathematics.float2 m_Height;
    public System.Single m_FadeSpeed;
    public System.Single m_Scale;
    public Unity.Entities.Entity m_GroupSoundNear;
    public Unity.Entities.Entity m_GroupSoundFar;
    public Unity.Mathematics.float2 m_NearHeight;
    public System.Single m_NearWeight;

}
```


## Fields

- `public Game.Simulation.GroupAmbienceType m_Type`  

```csharp
public Game.Simulation.GroupAmbienceType m_Type;
```

- `public Unity.Mathematics.float2 m_Height`  

```csharp
public Unity.Mathematics.float2 m_Height;
```

- `public System.Single m_FadeSpeed`  

```csharp
public System.Single m_FadeSpeed;
```

- `public System.Single m_Scale`  

```csharp
public System.Single m_Scale;
```

- `public Unity.Entities.Entity m_GroupSoundNear`  

```csharp
public Unity.Entities.Entity m_GroupSoundNear;
```

- `public Unity.Entities.Entity m_GroupSoundFar`  

```csharp
public Unity.Entities.Entity m_GroupSoundFar;
```

- `public Unity.Mathematics.float2 m_NearHeight`  

```csharp
public Unity.Mathematics.float2 m_NearHeight;
```

- `public System.Single m_NearWeight`  

```csharp
public System.Single m_NearWeight;
```


