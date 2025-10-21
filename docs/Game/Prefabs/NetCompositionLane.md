# Game.Prefabs.NetCompositionLane

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct NetCompositionLane : Unity.Entities.IBufferElementData
{
    public Unity.Entities.Entity m_Lane;
    public Unity.Mathematics.float3 m_Position;
    public Game.Prefabs.LaneFlags m_Flags;
    public System.Byte m_Carriageway;
    public System.Byte m_Group;
    public System.Byte m_Index;

    public NetCompositionLane(Game.Prefabs.DefaultNetLane source);

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

- `public Game.Prefabs.LaneFlags m_Flags`  

```csharp
public Game.Prefabs.LaneFlags m_Flags;
```

- `public System.Byte m_Carriageway`  

```csharp
public System.Byte m_Carriageway;
```

- `public System.Byte m_Group`  

```csharp
public System.Byte m_Group;
```

- `public System.Byte m_Index`  

```csharp
public System.Byte m_Index;
```


## Constructors

- `public NetCompositionLane(Game.Prefabs.DefaultNetLane source)`  

```csharp
public NetCompositionLane(Game.Prefabs.DefaultNetLane source);
```


