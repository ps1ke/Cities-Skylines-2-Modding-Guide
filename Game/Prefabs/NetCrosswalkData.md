# Game.Prefabs.NetCrosswalkData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct NetCrosswalkData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.Entity m_Lane;
    public Unity.Mathematics.float3 m_Start;
    public Unity.Mathematics.float3 m_End;

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


