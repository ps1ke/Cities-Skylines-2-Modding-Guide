# Game.Routes.PathTargets

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct PathTargets : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_StartLane;
    public Unity.Entities.Entity m_EndLane;
    public Unity.Mathematics.float2 m_CurvePositions;
    public Unity.Mathematics.float3 m_ReadyStartPosition;
    public Unity.Mathematics.float3 m_ReadyEndPosition;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_StartLane`  

```csharp
public Unity.Entities.Entity m_StartLane;
```

- `public Unity.Entities.Entity m_EndLane`  

```csharp
public Unity.Entities.Entity m_EndLane;
```

- `public Unity.Mathematics.float2 m_CurvePositions`  

```csharp
public Unity.Mathematics.float2 m_CurvePositions;
```

- `public Unity.Mathematics.float3 m_ReadyStartPosition`  

```csharp
public Unity.Mathematics.float3 m_ReadyStartPosition;
```

- `public Unity.Mathematics.float3 m_ReadyEndPosition`  

```csharp
public Unity.Mathematics.float3 m_ReadyEndPosition;
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


