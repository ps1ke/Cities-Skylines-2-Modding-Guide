# Game.Events.WeatherPhenomenon

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct WeatherPhenomenon : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Mathematics.float3 m_PhenomenonPosition;
    public Unity.Mathematics.float3 m_HotspotPosition;
    public Unity.Mathematics.float3 m_HotspotVelocity;
    public System.Single m_PhenomenonRadius;
    public System.Single m_HotspotRadius;
    public System.Single m_Intensity;
    public System.Single m_LightningTimer;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Mathematics.float3 m_PhenomenonPosition`  

```csharp
public Unity.Mathematics.float3 m_PhenomenonPosition;
```

- `public Unity.Mathematics.float3 m_HotspotPosition`  

```csharp
public Unity.Mathematics.float3 m_HotspotPosition;
```

- `public Unity.Mathematics.float3 m_HotspotVelocity`  

```csharp
public Unity.Mathematics.float3 m_HotspotVelocity;
```

- `public System.Single m_PhenomenonRadius`  

```csharp
public System.Single m_PhenomenonRadius;
```

- `public System.Single m_HotspotRadius`  

```csharp
public System.Single m_HotspotRadius;
```

- `public System.Single m_Intensity`  

```csharp
public System.Single m_Intensity;
```

- `public System.Single m_LightningTimer`  

```csharp
public System.Single m_LightningTimer;
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


