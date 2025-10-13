# Game.Prefabs.StorageCompanyData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`, `Game.Prefabs.ICombineData<Game.Prefabs.StorageCompanyData>`  

## Code

```csharp
public sealed struct StorageCompanyData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable, Game.Prefabs.ICombineData<Game.Prefabs.StorageCompanyData>
{
    public Game.Economy.Resource m_StoredResources;
    public Unity.Mathematics.int2 m_TransportInterval;

    public System.Void Combine(Game.Prefabs.StorageCompanyData otherData);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Economy.Resource m_StoredResources`  

```csharp
public Game.Economy.Resource m_StoredResources;
```

- `public Unity.Mathematics.int2 m_TransportInterval`  

```csharp
public Unity.Mathematics.int2 m_TransportInterval;
```


## Methods

- `public Combine(Game.Prefabs.StorageCompanyData otherData) : System.Void`  

```csharp
public void Combine(StorageCompanyData otherData)
	{
		m_StoredResources |= otherData.m_StoredResources;
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


