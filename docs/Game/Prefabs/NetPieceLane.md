# Game.Prefabs.NetPieceLane

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IComparable<Game.Prefabs.NetPieceLane>`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct NetPieceLane : Unity.Entities.IBufferElementData, System.IComparable<Game.Prefabs.NetPieceLane>
{
    public Unity.Entities.Entity m_Lane;
    public Unity.Mathematics.float3 m_Position;
    public Game.Prefabs.LaneFlags m_ExtraFlags;

    public System.Int32 CompareTo(Game.Prefabs.NetPieceLane other);
}
```


## Fields

- `public Unity.Entities.Entity m_Lane`  

```csharp
public Unity.Entities.Entity m_Lane;
```

- `public Unity.Mathematics.float3 m_Position`  

```csharp
public Unity.Mathematics.float3 m_Position;
```

- `public Game.Prefabs.LaneFlags m_ExtraFlags`  

```csharp
public Game.Prefabs.LaneFlags m_ExtraFlags;
```


## Methods

- `public CompareTo(Game.Prefabs.NetPieceLane other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.Prefabs.NetPieceLane other);
```


