# Game.Events.WaterLevelChange

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct WaterLevelChange : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Single m_Intensity;
    public System.Single m_MaxIntensity;
    public System.Single m_DangerHeight;
    public Unity.Mathematics.float2 m_Direction;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Single m_Intensity`  

```csharp
public System.Single m_Intensity;
```

- `public System.Single m_MaxIntensity`  

```csharp
public System.Single m_MaxIntensity;
```

- `public System.Single m_DangerHeight`  

```csharp
public System.Single m_DangerHeight;
```

- `public Unity.Mathematics.float2 m_Direction`  

```csharp
public Unity.Mathematics.float2 m_Direction;
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


