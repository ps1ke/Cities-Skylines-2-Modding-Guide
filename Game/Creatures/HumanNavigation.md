# Game.Creatures.HumanNavigation

**Assembly:** `Game`  
**Namespace:** `Game.Creatures`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct HumanNavigation : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Mathematics.float3 m_TargetPosition;
    public Unity.Mathematics.float2 m_TargetDirection;
    public System.Single m_MaxSpeed;
    public Game.Objects.TransformState m_TransformState;
    public System.Byte m_LastActivity;
    public System.Byte m_TargetActivity;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Mathematics.float3 m_TargetPosition`  

```csharp
public Unity.Mathematics.float3 m_TargetPosition;
```

- `public Unity.Mathematics.float2 m_TargetDirection`  

```csharp
public Unity.Mathematics.float2 m_TargetDirection;
```

- `public System.Single m_MaxSpeed`  

```csharp
public System.Single m_MaxSpeed;
```

- `public Game.Objects.TransformState m_TransformState`  

```csharp
public Game.Objects.TransformState m_TransformState;
```

- `public System.Byte m_LastActivity`  

```csharp
public System.Byte m_LastActivity;
```

- `public System.Byte m_TargetActivity`  

```csharp
public System.Byte m_TargetActivity;
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


