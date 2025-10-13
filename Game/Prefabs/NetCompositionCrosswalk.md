# Game.Prefabs.NetCompositionCrosswalk

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct NetCompositionCrosswalk : Unity.Entities.IBufferElementData
{
    public Unity.Entities.Entity m_Lane;
    public Unity.Mathematics.float3 m_Start;
    public Unity.Mathematics.float3 m_End;
    public Game.Prefabs.LaneFlags m_Flags;

}
```


## Fields

- `public Unity.Entities.Entity m_Lane`  

```csharp
public Unity.Entities.Entity m_Lane;
```

- `public Unity.Mathematics.float3 m_Start`  

```csharp
public Unity.Mathematics.float3 m_Start;
```

- `public Unity.Mathematics.float3 m_End`  

```csharp
public Unity.Mathematics.float3 m_End;
```

- `public Game.Prefabs.LaneFlags m_Flags`  

```csharp
public Game.Prefabs.LaneFlags m_Flags;
```


