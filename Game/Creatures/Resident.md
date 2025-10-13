# Game.Creatures.Resident

**Assembly:** `Game`  
**Namespace:** `Game.Creatures`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Resident : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Citizen;
    public Game.Creatures.ResidentFlags m_Flags;
    public System.Int32 m_Timer;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Citizen`  

```csharp
public Unity.Entities.Entity m_Citizen;
```

- `public Game.Creatures.ResidentFlags m_Flags`  

```csharp
public Game.Creatures.ResidentFlags m_Flags;
```

- `public System.Int32 m_Timer`  

```csharp
public System.Int32 m_Timer;
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


