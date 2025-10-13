# Game.Companies.TradeCost

**Assembly:** `Game`  
**Namespace:** `Game.Companies`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct TradeCost : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.ISerializable
{
    public Game.Economy.Resource m_Resource;
    public System.Single m_BuyCost;
    public System.Single m_SellCost;
    public System.Int64 m_LastTransferRequestTime;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Economy.Resource m_Resource`  

```csharp
public Game.Economy.Resource m_Resource;
```

- `public System.Single m_BuyCost`  

```csharp
public System.Single m_BuyCost;
```

- `public System.Single m_SellCost`  

```csharp
public System.Single m_SellCost;
```

- `public System.Int64 m_LastTransferRequestTime`  

```csharp
public System.Int64 m_LastTransferRequestTime;
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


