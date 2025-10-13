# Game.Companies.StorageTransferRequest

**Assembly:** `Game`  
**Namespace:** `Game.Companies`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct StorageTransferRequest : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.ISerializable
{
    public Game.Companies.StorageTransferFlags m_Flags;
    public Game.Economy.Resource m_Resource;
    public System.Int32 m_Amount;
    public Unity.Entities.Entity m_Target;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Companies.StorageTransferFlags m_Flags`  

```csharp
public Game.Companies.StorageTransferFlags m_Flags;
```

- `public Game.Economy.Resource m_Resource`  

```csharp
public Game.Economy.Resource m_Resource;
```

- `public System.Int32 m_Amount`  

```csharp
public System.Int32 m_Amount;
```

- `public Unity.Entities.Entity m_Target`  

```csharp
public Unity.Entities.Entity m_Target;
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


