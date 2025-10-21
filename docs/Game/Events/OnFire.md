# Game.Events.OnFire

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct OnFire : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Event;
    public Unity.Entities.Entity m_RescueRequest;
    public System.Single m_Intensity;
    public System.UInt32 m_RequestFrame;

    public OnFire(Unity.Entities.Entity _event, System.Single intensity, System.UInt32 requestFrame);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Event`  

```csharp
public Unity.Entities.Entity m_Event;
```

- `public Unity.Entities.Entity m_RescueRequest`  

```csharp
public Unity.Entities.Entity m_RescueRequest;
```

- `public System.Single m_Intensity`  

```csharp
public System.Single m_Intensity;
```

- `public System.UInt32 m_RequestFrame`  

```csharp
public System.UInt32 m_RequestFrame;
```


## Constructors

- `public OnFire(Unity.Entities.Entity _event, System.Single intensity, System.UInt32 requestFrame = 0)`  

```csharp
public OnFire(Unity.Entities.Entity _event, System.Single intensity, System.UInt32 requestFrame);
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


