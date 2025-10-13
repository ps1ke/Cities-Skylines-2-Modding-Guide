# Game.Prefabs.ResourceProductionData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct ResourceProductionData : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.ISerializable
{
    public Game.Economy.Resource m_Type;
    public System.Int32 m_ProductionRate;
    public System.Int32 m_StorageCapacity;

    public ResourceProductionData(Game.Economy.Resource type, System.Int32 productionRate, System.Int32 storageCapacity);

    public static System.Void Combine(Unity.Collections.NativeList<Game.Prefabs.ResourceProductionData> resources, Unity.Entities.DynamicBuffer<Game.Prefabs.ResourceProductionData> others);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Economy.Resource m_Type`  

```csharp
public Game.Economy.Resource m_Type;
```

- `public System.Int32 m_ProductionRate`  

```csharp
public System.Int32 m_ProductionRate;
```

- `public System.Int32 m_StorageCapacity`  

```csharp
public System.Int32 m_StorageCapacity;
```


## Constructors

- `public ResourceProductionData(Game.Economy.Resource type, System.Int32 productionRate, System.Int32 storageCapacity)`  

```csharp
public ResourceProductionData(Game.Economy.Resource type, System.Int32 productionRate, System.Int32 storageCapacity);
```


## Methods

- `public static Combine(Unity.Collections.NativeList<Game.Prefabs.ResourceProductionData> resources, Unity.Entities.DynamicBuffer<Game.Prefabs.ResourceProductionData> others) : System.Void`  

```csharp
public static System.Void Combine(Unity.Collections.NativeList<Game.Prefabs.ResourceProductionData> resources, Unity.Entities.DynamicBuffer<Game.Prefabs.ResourceProductionData> others);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


