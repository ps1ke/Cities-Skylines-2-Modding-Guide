# Game.Rendering.Swaying

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.IEmptySerializable`  

## Code

```csharp
public sealed struct Swaying : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Mathematics.float3 m_LastVelocity;
    public Unity.Mathematics.float3 m_SwayPosition;
    public Unity.Mathematics.float3 m_SwayVelocity;

}
```


## Fields

- `public Unity.Mathematics.float3 m_LastVelocity`  

```csharp
public Unity.Mathematics.float3 m_LastVelocity;
```

- `public Unity.Mathematics.float3 m_SwayPosition`  

```csharp
public Unity.Mathematics.float3 m_SwayPosition;
```

- `public Unity.Mathematics.float3 m_SwayVelocity`  

```csharp
public Unity.Mathematics.float3 m_SwayVelocity;
```


