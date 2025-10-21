# Game.Citizens.ResourceBought

**Assembly:** `Game`  
**Namespace:** `Game.Citizens`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct ResourceBought : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Seller;
    public Unity.Entities.Entity m_Payer;
    public Game.Economy.Resource m_Resource;
    public System.Int32 m_Amount;
    public System.Single m_Distance;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Seller`  

```csharp
public Unity.Entities.Entity m_Seller;
```

- `public Unity.Entities.Entity m_Payer`  

```csharp
public Unity.Entities.Entity m_Payer;
```

- `public Game.Economy.Resource m_Resource`  

```csharp
public Game.Economy.Resource m_Resource;
```

- `public System.Int32 m_Amount`  

```csharp
public System.Int32 m_Amount;
```

- `public System.Single m_Distance`  

```csharp
public System.Single m_Distance;
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


