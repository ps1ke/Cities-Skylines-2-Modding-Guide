# Game.City.ServiceImportBudget

**Assembly:** `Game`  
**Namespace:** `Game.City`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct ServiceImportBudget : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.ISerializable
{
    public Game.City.PlayerResource m_Resource;
    public System.Int32 m_MaximumBudget;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.City.PlayerResource m_Resource`  

```csharp
public Game.City.PlayerResource m_Resource;
```

- `public System.Int32 m_MaximumBudget`  

```csharp
public System.Int32 m_MaximumBudget;
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


