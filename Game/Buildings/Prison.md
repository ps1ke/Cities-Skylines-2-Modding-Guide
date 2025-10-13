# Game.Buildings.Prison

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Prison : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_TargetRequest;
    public Game.Buildings.PrisonFlags m_Flags;
    public System.SByte m_PrisonerWellbeing;
    public System.SByte m_PrisonerHealth;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_TargetRequest`  

```csharp
public Unity.Entities.Entity m_TargetRequest;
```

- `public Game.Buildings.PrisonFlags m_Flags`  

```csharp
public Game.Buildings.PrisonFlags m_Flags;
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

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


