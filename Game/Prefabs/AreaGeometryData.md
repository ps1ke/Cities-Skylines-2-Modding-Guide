# Game.Prefabs.AreaGeometryData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct AreaGeometryData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Areas.AreaType m_Type;
    public Game.Areas.GeometryFlags m_Flags;
    public System.Single m_SnapDistance;
    public System.Single m_MaxHeight;
    public System.Single m_LodBias;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Areas.AreaType m_Type`  

```csharp
public Game.Areas.AreaType m_Type;
```

- `public Game.Areas.GeometryFlags m_Flags`  

```csharp
public Game.Areas.GeometryFlags m_Flags;
```

- `public System.Single m_SnapDistance`  

```csharp
public System.Single m_SnapDistance;
```

- `public System.Single m_MaxHeight`  

```csharp
public System.Single m_MaxHeight;
```

- `public System.Single m_LodBias`  

```csharp
public System.Single m_LodBias;
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


