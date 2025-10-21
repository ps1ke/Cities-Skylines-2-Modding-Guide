# Game.Tools.Animation

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct Animation : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Mathematics.float3 m_TargetPosition;
    public Unity.Mathematics.float3 m_Position;
    public Unity.Mathematics.quaternion m_Rotation;
    public Unity.Mathematics.float3 m_SwayPivot;
    public Unity.Mathematics.float3 m_SwayPosition;
    public Unity.Mathematics.float3 m_SwayVelocity;
    public System.Single m_PushFactor;

    public Game.Objects.Transform ToTransform();
}
```


## Fields

- `public Unity.Mathematics.float3 m_TargetPosition`  

```csharp
public Unity.Mathematics.float3 m_TargetPosition;
```

- `public Unity.Mathematics.float3 m_Position`  

```csharp
public Unity.Mathematics.float3 m_Position;
```

- `public Unity.Mathematics.quaternion m_Rotation`  

```csharp
public Unity.Mathematics.quaternion m_Rotation;
```

- `public Unity.Mathematics.float3 m_SwayPivot`  

```csharp
public Unity.Mathematics.float3 m_SwayPivot;
```

- `public Unity.Mathematics.float3 m_SwayPosition`  

```csharp
public Unity.Mathematics.float3 m_SwayPosition;
```

- `public Unity.Mathematics.float3 m_SwayVelocity`  

```csharp
public Unity.Mathematics.float3 m_SwayVelocity;
```

- `public System.Single m_PushFactor`  

```csharp
public System.Single m_PushFactor;
```


## Methods

- `public ToTransform() : Game.Objects.Transform`  

```csharp
public Game.Objects.Transform ToTransform();
```


