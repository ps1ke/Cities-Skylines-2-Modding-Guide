# Game.Prefabs.TrainData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct TrainData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Net.TrackTypes m_TrackType;
    public Game.Vehicles.EnergyTypes m_EnergyType;
    public Game.Prefabs.TrainFlags m_TrainFlags;
    public System.Single m_MaxSpeed;
    public System.Single m_Acceleration;
    public System.Single m_Braking;
    public Unity.Mathematics.float2 m_Turning;
    public Unity.Mathematics.float2 m_BogieOffsets;
    public Unity.Mathematics.float2 m_AttachOffsets;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Net.TrackTypes m_TrackType`  

```csharp
public Game.Net.TrackTypes m_TrackType;
```

- `public Game.Vehicles.EnergyTypes m_EnergyType`  

```csharp
public Game.Vehicles.EnergyTypes m_EnergyType;
```

- `public Game.Prefabs.TrainFlags m_TrainFlags`  

```csharp
public Game.Prefabs.TrainFlags m_TrainFlags;
```

- `public System.Single m_MaxSpeed`  

```csharp
public System.Single m_MaxSpeed;
```

- `public System.Single m_Acceleration`  

```csharp
public System.Single m_Acceleration;
```

- `public System.Single m_Braking`  

```csharp
public System.Single m_Braking;
```

- `public Unity.Mathematics.float2 m_Turning`  

```csharp
public Unity.Mathematics.float2 m_Turning;
```

- `public Unity.Mathematics.float2 m_BogieOffsets`  

```csharp
public Unity.Mathematics.float2 m_BogieOffsets;
```

- `public Unity.Mathematics.float2 m_AttachOffsets`  

```csharp
public Unity.Mathematics.float2 m_AttachOffsets;
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


