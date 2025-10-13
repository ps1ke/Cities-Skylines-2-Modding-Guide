# Game.Creatures.Wildlife

**Assembly:** `Game`  
**Namespace:** `Game.Creatures`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Wildlife : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Creatures.WildlifeFlags m_Flags;
    public System.UInt16 m_StateTime;
    public System.UInt16 m_LifeTime;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Creatures.WildlifeFlags m_Flags`  

```csharp
public Game.Creatures.WildlifeFlags m_Flags;
```

- `public System.UInt16 m_StateTime`  

```csharp
public System.UInt16 m_StateTime;
```

- `public System.UInt16 m_LifeTime`  

```csharp
public System.UInt16 m_LifeTime;
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


