# Game.Prefabs.ExtractorAreaData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct ExtractorAreaData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Areas.MapFeature m_MapFeature;
    public System.Single m_ObjectSpawnFactor;
    public System.Single m_MaxObjectArea;
    public System.Boolean m_RequireNaturalResource;
    public System.Single m_WorkAmountFactor;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Areas.MapFeature m_MapFeature`  

```csharp
public Game.Areas.MapFeature m_MapFeature;
```

- `public System.Single m_ObjectSpawnFactor`  

```csharp
public System.Single m_ObjectSpawnFactor;
```

- `public System.Single m_MaxObjectArea`  

```csharp
public System.Single m_MaxObjectArea;
```

- `public System.Boolean m_RequireNaturalResource`  

```csharp
public System.Boolean m_RequireNaturalResource;
```

- `public System.Single m_WorkAmountFactor`  

```csharp
public System.Single m_WorkAmountFactor;
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


