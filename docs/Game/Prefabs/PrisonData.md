# Game.Prefabs.PrisonData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.PrisonData>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct PrisonData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Game.Prefabs.ICombineData<Game.Prefabs.PrisonData>, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_PrisonVanCapacity;
    public System.Int32 m_PrisonerCapacity;
    public System.SByte m_PrisonerWellbeing;
    public System.SByte m_PrisonerHealth;

    public System.Void Combine(Game.Prefabs.PrisonData otherData);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_PrisonVanCapacity`  

```csharp
public System.Int32 m_PrisonVanCapacity;
```

- `public System.Int32 m_PrisonerCapacity`  

```csharp
public System.Int32 m_PrisonerCapacity;
```

- `public System.SByte m_PrisonerWellbeing`  

```csharp
public System.SByte m_PrisonerWellbeing;
```

- `public System.SByte m_PrisonerHealth`  

```csharp
public System.SByte m_PrisonerHealth;
```


## Methods

- `public Combine(Game.Prefabs.PrisonData otherData) : System.Void`  

```csharp
public System.Void Combine(Game.Prefabs.PrisonData otherData);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


