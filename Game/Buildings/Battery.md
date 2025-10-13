# Game.Buildings.Battery

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Battery : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Int64 m_StoredEnergy;
    public System.Int32 m_Capacity;
    public System.Int32 m_LastFlow;

    public System.Int32 storedEnergyHours { get; }

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int64 m_StoredEnergy`  

```csharp
public System.Int64 m_StoredEnergy;
```

- `public System.Int32 m_Capacity`  

```csharp
public System.Int32 m_Capacity;
```

- `public System.Int32 m_LastFlow`  

```csharp
public System.Int32 m_LastFlow;
```


## Properties

- `public System.Int32 storedEnergyHours { get }`  

```csharp
public System.Int32 storedEnergyHours { get; }
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


