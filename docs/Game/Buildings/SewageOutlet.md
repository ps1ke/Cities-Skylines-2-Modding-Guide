# Game.Buildings.SewageOutlet

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct SewageOutlet : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_Capacity;
    public System.Int32 m_LastProcessed;
    public System.Int32 m_LastPurified;
    public System.Int32 m_UsedPurified;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_Capacity`  

```csharp
public System.Int32 m_Capacity;
```

- `public System.Int32 m_LastProcessed`  

```csharp
public System.Int32 m_LastProcessed;
```

- `public System.Int32 m_LastPurified`  

```csharp
public System.Int32 m_LastPurified;
```

- `public System.Int32 m_UsedPurified`  

```csharp
public System.Int32 m_UsedPurified;
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


