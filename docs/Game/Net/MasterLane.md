# Game.Net.MasterLane

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct MasterLane : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.UInt32 m_Group;
    public System.UInt16 m_MinIndex;
    public System.UInt16 m_MaxIndex;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.UInt32 m_Group`  

```csharp
public System.UInt32 m_Group;
```

- `public System.UInt16 m_MinIndex`  

```csharp
public System.UInt16 m_MinIndex;
```

- `public System.UInt16 m_MaxIndex`  

```csharp
public System.UInt16 m_MaxIndex;
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


