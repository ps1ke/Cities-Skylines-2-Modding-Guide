# Game.City.ServiceFee

**Assembly:** `Game`  
**Namespace:** `Game.City`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct ServiceFee : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.ISerializable
{
    public Game.City.PlayerResource m_Resource;
    public System.Single m_Fee;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Single GetDefaultFee(Game.City.PlayerResource resource);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.City.PlayerResource m_Resource`  

```csharp
public Game.City.PlayerResource m_Resource;
```

- `public System.Single m_Fee`  

```csharp
public System.Single m_Fee;
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetDefaultFee(Game.City.PlayerResource resource) : System.Single`  

```csharp
public System.Single GetDefaultFee(Game.City.PlayerResource resource);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


