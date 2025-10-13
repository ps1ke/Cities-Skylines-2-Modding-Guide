# Game.Prefabs.GarbageTruckData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct GarbageTruckData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_GarbageCapacity;
    public System.Int32 m_UnloadRate;

    public GarbageTruckData(System.Int32 garbageCapacity, System.Int32 unloadRate);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_GarbageCapacity`  

```csharp
public System.Int32 m_GarbageCapacity;
```

- `public System.Int32 m_UnloadRate`  

```csharp
public System.Int32 m_UnloadRate;
```


## Constructors

- `public GarbageTruckData(System.Int32 garbageCapacity, System.Int32 unloadRate)`  

```csharp
public GarbageTruckData(int garbageCapacity, int unloadRate)
	{
		m_GarbageCapacity = garbageCapacity;
		m_UnloadRate = unloadRate;
	}
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


