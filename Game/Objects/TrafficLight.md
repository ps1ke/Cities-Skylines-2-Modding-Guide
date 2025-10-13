# Game.Objects.TrafficLight

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct TrafficLight : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Objects.TrafficLightState m_State;
    public System.UInt16 m_GroupMask0;
    public System.UInt16 m_GroupMask1;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Objects.TrafficLightState m_State`  

```csharp
public Game.Objects.TrafficLightState m_State;
```

- `public System.UInt16 m_GroupMask0`  

```csharp
public System.UInt16 m_GroupMask0;
```

- `public System.UInt16 m_GroupMask1`  

```csharp
public System.UInt16 m_GroupMask1;
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


