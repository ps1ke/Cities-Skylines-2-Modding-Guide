# Game.City.XP

**Assembly:** `Game`  
**Namespace:** `Game.City`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct XP : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_XP;
    public System.Int32 m_MaximumPopulation;
    public System.Int32 m_MaximumIncome;
    public Game.City.XPRewardFlags m_XPRewardRecord;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_XP`  

```csharp
public System.Int32 m_XP;
```

- `public System.Int32 m_MaximumPopulation`  

```csharp
public System.Int32 m_MaximumPopulation;
```

- `public System.Int32 m_MaximumIncome`  

```csharp
public System.Int32 m_MaximumIncome;
```

- `public Game.City.XPRewardFlags m_XPRewardRecord`  

```csharp
public Game.City.XPRewardFlags m_XPRewardRecord;
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


