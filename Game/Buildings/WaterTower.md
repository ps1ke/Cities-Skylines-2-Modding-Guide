# Game.Buildings.WaterTower

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct WaterTower : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_StoredWater;
    public System.Int32 m_Polluted;
    public System.Int32 m_LastStoredWater;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_StoredWater`  

```csharp
public System.Int32 m_StoredWater;
```

- `public System.Int32 m_Polluted`  

```csharp
public System.Int32 m_Polluted;
```

- `public System.Int32 m_LastStoredWater`  

```csharp
public System.Int32 m_LastStoredWater;
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


