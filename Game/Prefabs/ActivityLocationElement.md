# Game.Prefabs.ActivityLocationElement

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct ActivityLocationElement : Unity.Entities.IBufferElementData
{
    public Unity.Entities.Entity m_Prefab;
    public Game.Prefabs.ActivityMask m_ActivityMask;
    public Game.Prefabs.ActivityFlags m_ActivityFlags;
    public Unity.Mathematics.float3 m_Position;
    public Unity.Mathematics.quaternion m_Rotation;
    public Game.Rendering.AnimatedPropID m_PropID;

}
```


## Fields

- `public Unity.Entities.Entity m_Prefab`  

```csharp
public Unity.Entities.Entity m_Prefab;
```

- `public Game.Prefabs.ActivityMask m_ActivityMask`  

```csharp
public Game.Prefabs.ActivityMask m_ActivityMask;
```

- `public Game.Prefabs.ActivityFlags m_ActivityFlags`  

```csharp
public Game.Prefabs.ActivityFlags m_ActivityFlags;
```

- `public Unity.Mathematics.float3 m_Position`  

```csharp
public Unity.Mathematics.float3 m_Position;
```

- `public Unity.Mathematics.quaternion m_Rotation`  

```csharp
public Unity.Mathematics.quaternion m_Rotation;
```

- `public Game.Rendering.AnimatedPropID m_PropID`  

```csharp
public Game.Rendering.AnimatedPropID m_PropID;
```


