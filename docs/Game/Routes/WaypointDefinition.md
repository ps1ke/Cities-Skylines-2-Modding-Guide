# Game.Routes.WaypointDefinition

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct WaypointDefinition : Unity.Entities.IBufferElementData
{
    public Unity.Mathematics.float3 m_Position;
    public Unity.Entities.Entity m_Connection;
    public Unity.Entities.Entity m_Original;

    public WaypointDefinition(Unity.Mathematics.float3 position);

}
```


## Fields

- `public Unity.Mathematics.float3 m_Position`  

```csharp
public Unity.Mathematics.float3 m_Position;
```

- `public Unity.Entities.Entity m_Connection`  

```csharp
public Unity.Entities.Entity m_Connection;
```

- `public Unity.Entities.Entity m_Original`  

```csharp
public Unity.Entities.Entity m_Original;
```


## Constructors

- `public WaypointDefinition(Unity.Mathematics.float3 position)`  

```csharp
public WaypointDefinition(Unity.Mathematics.float3 position);
```


