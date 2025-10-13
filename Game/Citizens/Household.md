# Game.Citizens.Household

**Assembly:** `Game`  
**Namespace:** `Game.Citizens`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Household : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Citizens.HouseholdFlags m_Flags;
    public System.Int32 m_Resources;
    public System.Int16 m_ConsumptionPerDay;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Citizens.HouseholdFlags m_Flags`  

```csharp
public Game.Citizens.HouseholdFlags m_Flags;
```

- `public System.Int32 m_Resources`  

```csharp
public System.Int32 m_Resources;
```

- `public System.Int16 m_ConsumptionPerDay`  

```csharp
public System.Int16 m_ConsumptionPerDay;
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


