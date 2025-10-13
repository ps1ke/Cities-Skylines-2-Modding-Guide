# Game.Routes.TaxiStand

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct TaxiStand : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_TaxiRequest;
    public Game.Routes.TaxiStandFlags m_Flags;
    public System.UInt16 m_StartingFee;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_TaxiRequest`  

```csharp
public Unity.Entities.Entity m_TaxiRequest;
```

- `public Game.Routes.TaxiStandFlags m_Flags`  

```csharp
public Game.Routes.TaxiStandFlags m_Flags;
```

- `public System.UInt16 m_StartingFee`  

```csharp
public System.UInt16 m_StartingFee;
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


