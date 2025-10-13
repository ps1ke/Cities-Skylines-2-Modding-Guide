# Game.Prefabs.AuxiliaryNet

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct AuxiliaryNet : Unity.Entities.IBufferElementData
{
    public Unity.Entities.Entity m_Prefab;
    public Unity.Mathematics.float3 m_Position;
    public Game.Prefabs.NetInvertMode m_InvertMode;

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

- `public Game.Prefabs.NetInvertMode m_InvertMode`  

```csharp
public Game.Prefabs.NetInvertMode m_InvertMode;
```


