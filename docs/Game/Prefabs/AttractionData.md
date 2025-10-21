# Game.Prefabs.AttractionData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.AttractionData>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct AttractionData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Game.Prefabs.ICombineData<Game.Prefabs.AttractionData>, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_Attractiveness;

    public System.Void Combine(Game.Prefabs.AttractionData otherData);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_Attractiveness`  

```csharp
public System.Int32 m_Attractiveness;
```


## Methods

- `public Combine(Game.Prefabs.AttractionData otherData) : System.Void`  

```csharp
public System.Void Combine(Game.Prefabs.AttractionData otherData);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


