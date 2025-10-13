# Game.Prefabs.LocalConnectData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct LocalConnectData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Prefabs.LocalConnectFlags m_Flags;
    public Game.Net.Layer m_Layers;
    public Colossal.Mathematics.Bounds1 m_HeightRange;
    public System.Single m_SearchDistance;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Prefabs.LocalConnectFlags m_Flags`  

```csharp
public Game.Prefabs.LocalConnectFlags m_Flags;
```

- `public Game.Net.Layer m_Layers`  

```csharp
public Game.Net.Layer m_Layers;
```

- `public Colossal.Mathematics.Bounds1 m_HeightRange`  

```csharp
public Colossal.Mathematics.Bounds1 m_HeightRange;
```

- `public System.Single m_SearchDistance`  

```csharp
public System.Single m_SearchDistance;
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


