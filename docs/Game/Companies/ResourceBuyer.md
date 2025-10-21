# Game.Companies.ResourceBuyer

**Assembly:** `Game`  
**Namespace:** `Game.Companies`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct ResourceBuyer : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Payer;
    public Game.Pathfind.SetupTargetFlags m_Flags;
    public Game.Economy.Resource m_ResourceNeeded;
    public System.Int32 m_AmountNeeded;
    public Unity.Mathematics.float3 m_Location;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Payer`  

```csharp
public Unity.Entities.Entity m_Payer;
```

- `public Game.Pathfind.SetupTargetFlags m_Flags`  

```csharp
public Game.Pathfind.SetupTargetFlags m_Flags;
```

- `public Game.Economy.Resource m_ResourceNeeded`  

```csharp
public Game.Economy.Resource m_ResourceNeeded;
```

- `public System.Int32 m_AmountNeeded`  

```csharp
public System.Int32 m_AmountNeeded;
```

- `public Unity.Mathematics.float3 m_Location`  

```csharp
public Unity.Mathematics.float3 m_Location;
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


