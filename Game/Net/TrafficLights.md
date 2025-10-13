# Game.Net.TrafficLights

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct TrafficLights : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Net.TrafficLightState m_State;
    public Game.Net.TrafficLightFlags m_Flags;
    public System.Byte m_SignalGroupCount;
    public System.Byte m_CurrentSignalGroup;
    public System.Byte m_NextSignalGroup;
    public System.Byte m_Timer;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Net.TrafficLightState m_State`  

```csharp
public Game.Net.TrafficLightState m_State;
```

- `public Game.Net.TrafficLightFlags m_Flags`  

```csharp
public Game.Net.TrafficLightFlags m_Flags;
```

- `public System.Byte m_SignalGroupCount`  

```csharp
public System.Byte m_SignalGroupCount;
```

- `public System.Byte m_CurrentSignalGroup`  

```csharp
public System.Byte m_CurrentSignalGroup;
```

- `public System.Byte m_NextSignalGroup`  

```csharp
public System.Byte m_NextSignalGroup;
```

- `public System.Byte m_Timer`  

```csharp
public System.Byte m_Timer;
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


