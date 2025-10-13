# Game.Prefabs.AuxiliaryNetLane

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct AuxiliaryNetLane : Unity.Entities.IBufferElementData
{
    public Unity.Entities.Entity m_Prefab;
    public Unity.Mathematics.float3 m_Position;
    public Unity.Mathematics.float3 m_Spacing;
    public Game.Prefabs.CompositionFlags m_CompositionAll;
    public Game.Prefabs.CompositionFlags m_CompositionAny;
    public Game.Prefabs.CompositionFlags m_CompositionNone;
    public Game.Prefabs.LaneFlags m_Flags;

}
```


## Fields

- `public Unity.Entities.Entity m_Prefab`  

```csharp
public Unity.Entities.Entity m_Prefab;
```

- `public Unity.Mathematics.float3 m_Position`  

```csharp
public Unity.Mathematics.float3 m_Position;
```

- `public Unity.Mathematics.float3 m_Spacing`  

```csharp
public Unity.Mathematics.float3 m_Spacing;
```

- `public Game.Prefabs.CompositionFlags m_CompositionAll`  

```csharp
public Game.Prefabs.CompositionFlags m_CompositionAll;
```

- `public Game.Prefabs.CompositionFlags m_CompositionAny`  

```csharp
public Game.Prefabs.CompositionFlags m_CompositionAny;
```

- `public Game.Prefabs.CompositionFlags m_CompositionNone`  

```csharp
public Game.Prefabs.CompositionFlags m_CompositionNone;
```

- `public Game.Prefabs.LaneFlags m_Flags`  

```csharp
public Game.Prefabs.LaneFlags m_Flags;
```


