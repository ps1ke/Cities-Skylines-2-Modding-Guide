# Game.Objects.UnderConstruction

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `FormerlySerializedAs`  

## Code

```csharp
public sealed struct UnderConstruction : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_NewPrefab;
    public System.Byte m_Progress;
    public System.Byte m_Speed;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_NewPrefab`  

```csharp
public Unity.Entities.Entity m_NewPrefab;
```

- `public System.Byte m_Progress`  

```csharp
public System.Byte m_Progress;
```

- `public System.Byte m_Speed`  

```csharp
public System.Byte m_Speed;
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


